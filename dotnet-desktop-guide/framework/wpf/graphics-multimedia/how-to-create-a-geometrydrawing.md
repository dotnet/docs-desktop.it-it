---
title: 'Procedura: creare un oggetto GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967981"
---
# <a name="how-to-create-a-geometrydrawing"></a>Procedura: creare un oggetto GeometryDrawing
Questo esempio illustra come creare e visualizzare un oggetto <xref:System.Windows.Media.GeometryDrawing> . Un oggetto <xref:System.Windows.Media.GeometryDrawing> consente di creare una forma con un riempimento e un contorno associando un oggetto <xref:System.Windows.Media.Pen> e un oggetto a un oggetto <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Geometry> . <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>Descrive la struttura della forma, <xref:System.Windows.Media.GeometryDrawing.Brush%2A> che descrive il riempimento della forma e <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive il contorno della forma.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.GeometryDrawing> per eseguire il rendering di una forma. La forma è descritta da un oggetto <xref:System.Windows.Media.GeometryGroup> e da due <xref:System.Windows.Media.EllipseGeometry> oggetti. L'interno della forma viene disegnato con un oggetto <xref:System.Windows.Media.LinearGradientBrush> e il contorno viene disegnato con un oggetto <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> . <xref:System.Windows.Media.GeometryDrawing>Viene visualizzato utilizzando un oggetto <xref:System.Windows.Media.ImageDrawing> e un <xref:System.Windows.Controls.Image> elemento.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 La figura seguente mostra l'oggetto risultante <xref:System.Windows.Media.GeometryDrawing> .  
  
 ![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Per creare disegni più complessi, è possibile combinare più oggetti Drawing in un singolo disegno composto usando un oggetto <xref:System.Windows.Media.DrawingGroup> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare un disegno composto](how-to-create-a-composite-drawing.md)
