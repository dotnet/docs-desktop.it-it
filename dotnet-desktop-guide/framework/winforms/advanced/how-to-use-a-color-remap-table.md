---
title: 'Procedura: Usare una tabella per modificare il mapping dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962461"
---
# <a name="how-to-use-a-color-remap-table"></a>Procedura: Usare una tabella per modificare il mapping dei colori
Il rimapping è il processo di conversione dei colori in un'immagine in base a una tabella di modifica del mapping dei colori. La tabella di modifica del mapping dei colori è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Ogni <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice ha una <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e una <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Proprietà.  
  
 Quando GDI+ disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice dei colori precedenti. Se il colore di un pixel corrisponde a un colore precedente, il colore viene modificato nel nuovo colore corrispondente. I colori vengono modificati solo per il rendering: i valori dei colori dell'immagine stessa (archiviati in <xref:System.Drawing.Image> un <xref:System.Drawing.Bitmap> oggetto o) non vengono modificati.  
  
 Per tracciare un'immagine rimappata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Passare la matrice al <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> oggetto, quindi passare l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Image> oggetto dal file RemapInput.bmp. Il codice crea una tabella di modifica del mapping dei colori costituita da un singolo <xref:System.Drawing.Imaging.ColorMap> oggetto. La <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà dell' `ColorRemap` oggetto è rossa e la <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è blu. L'immagine viene disegnata una volta senza modificarne il mapping e una volta con il mapping. Il processo di modifica del mapping modifica tutti i pixel rossi in blu.  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine rimappata a destra.  
  
 ![Screenshot che mostra l'immagine originale e l'immagine rimappata.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Ricolorazione di immagini](recoloring-images.md)
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
