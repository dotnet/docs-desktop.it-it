---
title: 'Procedura: Migliorare le prestazioni evitando il ridimensionamento automatico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962608"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Procedura: Migliorare le prestazioni evitando il ridimensionamento automatico
GDI+ può ridimensionare automaticamente un'immagine mentre viene disegnato, riducendo le prestazioni. In alternativa, è possibile controllare il ridimensionamento dell'immagine passando le dimensioni del rettangolo di destinazione al <xref:System.Drawing.Graphics.DrawImage%2A> metodo.  
  
 Ad esempio, la chiamata seguente al <xref:System.Drawing.Graphics.DrawImage%2A> metodo specifica un angolo superiore sinistro di (50, 30) ma non specifica un rettangolo di destinazione.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Sebbene si tratta della versione più semplice del <xref:System.Drawing.Graphics.DrawImage%2A> metodo in termini di numero di argomenti obbligatori, non è necessariamente il più efficiente. Se la risoluzione usata da GDI+ (in genere 96 punti per pollice) è diversa dalla risoluzione archiviata nell' <xref:System.Drawing.Image> oggetto, il <xref:System.Drawing.Graphics.DrawImage%2A> metodo ridimensiona l'immagine. Si supponga, ad esempio, <xref:System.Drawing.Image> che un oggetto abbia una larghezza di 216 pixel e un valore di risoluzione orizzontale archiviato di 72 punti per pollice. Poiché 216/72 è 3, <xref:System.Drawing.Graphics.DrawImage%2A> Ridimensiona l'immagine in modo che abbia una larghezza di 3 centimetri a una risoluzione di 96 punti per pollice. Ovvero <xref:System.Drawing.Graphics.DrawImage%2A> visualizzerà un'immagine con una larghezza di 96x3 = 288 pixel.  
  
 Anche se la risoluzione dello schermo è diversa da 96 punti per pollice, GDI+ potrebbe ridimensionare l'immagine come se la risoluzione dello schermo fosse 96 punti per pollice. Ciò è dovuto al fatto che un <xref:System.Drawing.Graphics> oggetto GDI+ è associato a un contesto di dispositivo e quando GDI+ esegue una query sul contesto di dispositivo per la risoluzione dello schermo, il risultato è in genere 96, indipendentemente dalla risoluzione effettiva dello schermo. È possibile evitare il ridimensionamento automatico specificando il rettangolo di destinazione nel <xref:System.Drawing.Graphics.DrawImage%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnata due volte la stessa immagine. Nel primo caso, la larghezza e l'altezza del rettangolo di destinazione non sono specificate e l'immagine viene ridimensionata automaticamente. Nel secondo caso, la larghezza e l'altezza (misurate in pixel) del rettangolo di destinazione vengono specificate come la larghezza e l'altezza dell'immagine originale. La figura seguente mostra il rendering dell'immagine due volte:  
  
 ![Screenshot che mostra le immagini con trama ridimensionata.](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire Texture.jpg con il nome e il percorso di un'immagine validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
