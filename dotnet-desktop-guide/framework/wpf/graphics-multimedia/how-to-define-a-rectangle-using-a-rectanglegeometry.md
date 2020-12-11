---
title: 'Procedura: definire un rettangolo utilizzando RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967324"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Procedura: definire un rettangolo utilizzando RectangleGeometry
Questo esempio descrive come usare la <xref:System.Windows.Media.RectangleGeometry> classe per descrivere un rettangolo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.RectangleGeometry> .  La posizione relativa e le dimensioni del rettangolo sono definite da una <xref:System.Windows.Rect> struttura. La posizione relativa è `50,50` e l'altezza e la larghezza sono entrambe la `25` creazione di un quadrato. L'interno del rettangolo viene disegnato con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pennello e il contorno viene disegnato con un <xref:System.Windows.Media.Brushes.Black%2A> tratto con uno spessore pari a `1` .  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![Oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Sebbene in questo esempio venga utilizzato un <xref:System.Windows.Shapes.Path> elemento per eseguire il rendering di <xref:System.Windows.Media.RectangleGeometry> , è possibile utilizzare gli oggetti in molti altri modi <xref:System.Windows.Media.RectangleGeometry> . È ad esempio <xref:System.Windows.Media.RectangleGeometry> possibile utilizzare un oggetto per specificare l'oggetto <xref:System.Windows.UIElement.Clip%2A> di un oggetto <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> di un oggetto <xref:System.Windows.Media.GeometryDrawing> .  
  
 Altre classi Geometry semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry> . Queste geometrie, così come quelle più complesse, possono essere create anche usando <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry> .  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
