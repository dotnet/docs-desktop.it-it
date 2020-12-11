---
title: 'Procedura: Disegnare una bitmap esistente sullo schermo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962695"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Procedura: Disegnare una bitmap esistente sullo schermo
È possibile creare facilmente un'immagine esistente sullo schermo. Per prima cosa è necessario creare un <xref:System.Drawing.Bitmap> oggetto usando il costruttore bitmap che accetta un nome file, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29> . Questo costruttore accetta immagini con diversi formati di file, tra cui BMP, GIF, JPEG, PNG e TIFF. Dopo aver creato l' <xref:System.Drawing.Bitmap> oggetto, passare <xref:System.Drawing.Bitmap> l'oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Questo esempio crea un <xref:System.Drawing.Bitmap> oggetto da un file JPEG, quindi disegna la bitmap con l'angolo superiore sinistro in corrispondenza di (60, 10).  
  
 Nella figura seguente viene illustrata la bitmap disegnata nel percorso specificato:  
  
 ![Screenshot che mostra un'immagine in una posizione specificata.](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
