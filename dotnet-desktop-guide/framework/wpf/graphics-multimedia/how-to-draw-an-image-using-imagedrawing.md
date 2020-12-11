---
title: 'Procedura: disegnare un’immagine con ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951254"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Procedura: disegnare un’immagine con ImageDrawing
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ImageDrawing> per creare un'immagine. Un oggetto <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un oggetto <xref:System.Windows.Media.ImageSource> con <xref:System.Windows.Media.DrawingBrush> , <xref:System.Windows.Media.DrawingImage> o <xref:System.Windows.Media.Visual> . Per creare un'immagine, è necessario creare un oggetto <xref:System.Windows.Media.ImageDrawing> e impostare le relative <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà e. La <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da creare e la <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e le dimensioni di ogni immagine.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un disegno composito utilizzando quattro <xref:System.Windows.Media.ImageDrawing> oggetti. Questo esempio genera l'immagine seguente:  
  
 ![Alcuni oggetti DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
Quattro oggetti ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Per un esempio in cui viene illustrato un modo semplice per visualizzare un'immagine senza usare <xref:System.Windows.Media.ImageDrawing> , vedere [usare l'elemento Image](../controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Attributo PresentationOptions:Freeze](../advanced/presentationoptions-freeze-attribute.md)
