---
title: 'Procedura: utilizzare un disegno come origine di immagini'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961267"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Procedura: utilizzare un disegno come origine di immagini
Questo esempio illustra come usare <xref:System.Windows.Media.Drawing> come <xref:System.Windows.Controls.Image.Source%2A> per un <xref:System.Windows.Controls.Image> controllo. Per visualizzare un <xref:System.Windows.Media.Drawing> oggetto con un <xref:System.Windows.Controls.Image> controllo, usare un <xref:System.Windows.Media.DrawingImage> oggetto come oggetto del <xref:System.Windows.Controls.Image> controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare la <xref:System.Windows.Media.DrawingImage> proprietà dell'oggetto sul <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> disegno che si vuole visualizzare.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Media.DrawingImage> e un <xref:System.Windows.Controls.Image> controllo per visualizzare un oggetto <xref:System.Windows.Media.GeometryDrawing> . Nell'esempio viene prodotto l'output seguente:  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable.Freeze%2A>
- [Disegnare un'immagine con ImageDrawing](how-to-draw-an-image-using-imagedrawing.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Attributo PresentationOptions:Freeze](../advanced/presentationoptions-freeze-attribute.md)
