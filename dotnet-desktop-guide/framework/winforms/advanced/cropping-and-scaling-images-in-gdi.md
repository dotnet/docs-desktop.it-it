---
title: Ritaglio e ridimensionamento di immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952470"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Ritaglio e ridimensionamento di immagini in GDI+
È possibile usare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo della <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e immagini raster. <xref:System.Drawing.Graphics.DrawImage%2A> è un metodo di overload, quindi è possibile fornire gli argomenti in diversi modi.  
  
## <a name="drawimage-variations"></a>Variazioni di DrawImage  
 Una variante del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un oggetto <xref:System.Drawing.Bitmap> e un oggetto <xref:System.Drawing.Rectangle> . Il rettangolo specifica la destinazione per l'operazione di disegno. ovvero specifica il rettangolo in cui si desidera creare l'immagine. Se le dimensioni del rettangolo di destinazione sono diverse da quelle dell'immagine originale, l'immagine viene ridimensionata in modo da adattarsi al rettangolo di destinazione. Nell'esempio di codice seguente viene illustrato come creare la stessa immagine tre volte: una volta senza scalabilità, una volta con un'espansione e una volta con una compressione:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Nella figura seguente sono illustrate le tre immagini.  
  
 ![Ridimensionamento](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Alcune varianti del <xref:System.Drawing.Graphics.DrawImage%2A> Metodo hanno un parametro source-Rectangle, oltre a un parametro Destination-Rectangle. Il parametro source-Rectangle specifica la parte dell'immagine originale da creare. Il rettangolo di destinazione specifica il rettangolo in cui creare la parte dell'immagine. Se le dimensioni del rettangolo di destinazione sono diverse dalla dimensione del rettangolo di origine, l'immagine viene ridimensionata in modo da adattarsi al rettangolo di destinazione.  
  
 Nell'esempio di codice seguente viene illustrato come costruire un oggetto <xref:System.Drawing.Bitmap> dal file Runner.jpg. L'intera immagine viene disegnata senza alcun ridimensionamento in corrispondenza di (0, 0). Una piccola parte dell'immagine viene disegnata due volte: una volta con una compressione e una volta con un'espansione.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Nella figura seguente viene illustrata l'immagine non ridimensionata e le parti di immagine compresse ed espanse.  
  
 ![Ritaglio e ridimensionamento](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
