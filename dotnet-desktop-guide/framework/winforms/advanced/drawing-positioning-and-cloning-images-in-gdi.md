---
title: Disegno, posizionamento e duplicazione delle immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960733"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Disegno, posizionamento e duplicazione delle immagini in GDI+
È possibile usare la <xref:System.Drawing.Bitmap> classe per caricare e visualizzare immagini raster ed è possibile usare la <xref:System.Drawing.Imaging.Metafile> classe per caricare e visualizzare le immagini vettoriali. Le <xref:System.Drawing.Bitmap> <xref:System.Drawing.Imaging.Metafile> classi e ereditano dalla <xref:System.Drawing.Image> classe. Per visualizzare un'immagine vettoriale, è necessario disporre di un'istanza della <xref:System.Drawing.Graphics> classe e di un oggetto <xref:System.Drawing.Imaging.Metafile> . Per visualizzare un'immagine raster, è necessario disporre di un'istanza della <xref:System.Drawing.Graphics> classe e di un oggetto <xref:System.Drawing.Bitmap> . L'istanza della <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawImage%2A> metodo, che riceve <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> come argomento.  
  
## <a name="file-types-and-cloning"></a>Tipi di file e clonazione  
 Nell'esempio di codice seguente viene illustrato come costruire un oggetto <xref:System.Drawing.Bitmap> dal file Climber.jpg e visualizzare la bitmap. Il punto di destinazione per l'angolo superiore sinistro dell'immagine, (10, 10), viene specificato nel secondo e nel terzo parametro.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 Nell'illustrazione seguente viene mostrata l'immagine.  
  
 ![Esempio Image](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 È possibile costruire <xref:System.Drawing.Bitmap> oggetti da diversi formati di file di grafica: BMP, gif, JPEG, EXIF, PNG, TIFF e Icon.  
  
 Nell'esempio di codice seguente viene illustrato come costruire <xref:System.Drawing.Bitmap> oggetti da un'ampia gamma di tipi di file e quindi visualizzare le bitmap.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 La <xref:System.Drawing.Bitmap> classe fornisce un <xref:System.Drawing.Bitmap.Clone%2A> metodo che è possibile utilizzare per creare una copia di un oggetto esistente <xref:System.Drawing.Bitmap> . Il <xref:System.Drawing.Bitmap.Clone%2A> metodo dispone di un parametro Rectangle di origine che è possibile utilizzare per specificare la parte della bitmap originale che si desidera copiare. Nell'esempio di codice seguente viene illustrato come creare un oggetto <xref:System.Drawing.Bitmap> clonando la metà superiore di un oggetto esistente <xref:System.Drawing.Bitmap> . Vengono quindi disegnate entrambe le immagini.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 Nella figura seguente sono illustrate le due immagini.  
  
 ![Ritaglio](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
