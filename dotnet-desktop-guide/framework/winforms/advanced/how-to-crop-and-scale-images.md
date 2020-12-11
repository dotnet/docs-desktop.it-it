---
title: 'Procedura: Ritagliare e modificare le dimensioni di immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951459"
---
# <a name="how-to-crop-and-scale-images"></a>Procedura: Ritagliare e modificare le dimensioni di immagini
La <xref:System.Drawing.Graphics> classe fornisce diversi <xref:System.Drawing.Graphics.DrawImage%2A> metodi, alcuni dei quali hanno parametri di origine e di destinazione rettangolari che è possibile usare per ritagliare e ridimensionare le immagini.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file su disco Apple.gif. Il codice disegna l'intera immagine Apple nelle dimensioni originali. Il codice chiama quindi il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto per creare una parte dell'immagine Apple in un rettangolo di destinazione più grande dell'immagine Apple originale.  
  
 Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la parte della mela da creare osservando il rettangolo di origine, specificato dal terzo, dal quarto, dal quinto e dal sesto argomento. In questo caso, la mela viene ritagliata al 75% della larghezza e il 75% dell'altezza.  
  
 Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la posizione in cui creare la mela ritagliata e la dimensione della mela ritagliata esaminando il rettangolo di destinazione, specificato dal secondo argomento. In questo caso, il rettangolo di destinazione è più grande del 30% e il 30% più alto rispetto all'immagine originale.  
  
 La figura seguente mostra l'Apple originale e l'Apple ritagliata e ridimensionata.  
  
 ![Screenshot di un'immagine originale e della stessa immagine ritagliata.](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Assicurarsi di sostituire `Apple.gif` con il nome e il percorso di un file di immagine validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
