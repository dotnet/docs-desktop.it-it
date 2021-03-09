---
title: 'Procedura: creare una curva di Bezier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: b7a1ce63a4869d17eb1d34c486ab7a335d3528d1
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511619"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Procedura: creare una curva di Bezier cubica
Questo esempio illustra come creare una curva di Bezier cubica. Per creare una curva di Bezier cubica, usare le <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.BezierSegment> .  Per visualizzare la geometria risultante, utilizzare un <xref:System.Windows.Shapes.Path> elemento o utilizzarlo con un oggetto <xref:System.Windows.Media.GeometryDrawing> o un oggetto <xref:System.Windows.Media.DrawingContext> . Negli esempi seguenti viene disegnata una curva di Bezier cubica da (10, 100) a (300, 100). La curva ha punti di controllo di (100, 0) e (200, 200).  
  
## <a name="example"></a>Esempio  

 In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare la sintassi di markup abbreviata per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]
  
 In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile creare una curva di Bezier cubica usando i tag Object. L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Vedi anche

- [Creare un arco ellittico](how-to-create-an-elliptical-arc.md)
- [Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
- [Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md)
