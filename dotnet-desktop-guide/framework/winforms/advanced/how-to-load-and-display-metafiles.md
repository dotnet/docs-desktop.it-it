---
title: 'Procedura: Caricare e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962593"
---
# <a name="how-to-load-and-display-metafiles"></a>Procedura: Caricare e visualizzare metafile
La <xref:System.Drawing.Imaging.Metafile> classe, che eredita dalla <xref:System.Drawing.Image> classe, fornisce metodi per la registrazione, la visualizzazione e l'analisi di immagini vettoriali.  
  
## <a name="example"></a>Esempio  
 Per visualizzare un'immagine vettoriale (Metafile) sullo schermo, sono necessari un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto. Passare il nome di un file (o di un flusso) a un <xref:System.Drawing.Imaging.Metafile> costruttore. Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> oggetto, passare <xref:System.Drawing.Imaging.Metafile> l'oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (Enhanced Metafile), quindi viene disegnata l'immagine con l'angolo superiore sinistro in (60, 10).  
  
 Nella figura seguente viene illustrato il metafile disegnato nella posizione specificata.  
  
 ![Screenshot che mostra la posizione dell'immagine.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
