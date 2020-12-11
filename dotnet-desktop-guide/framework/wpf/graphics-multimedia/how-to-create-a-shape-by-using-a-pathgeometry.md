---
title: 'Procedura: creare una forma tramite un oggetto PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967675"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Procedura: creare una forma tramite un oggetto PathGeometry
Questo esempio illustra come creare una forma usando la <xref:System.Windows.Media.PathGeometry> classe. <xref:System.Windows.Media.PathGeometry> gli oggetti sono costituiti da uno o più <xref:System.Windows.Media.PathFigure> oggetti, ognuno dei quali <xref:System.Windows.Media.PathFigure> rappresenta una "figura" o una forma diversa. Ognuno <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali rappresenta una parte connessa della figura o della forma. I tipi di segmento includono <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.ArcSegment> e <xref:System.Windows.Media.BezierSegment> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.PathGeometry> per creare un triangolo. <xref:System.Windows.Media.PathGeometry>Viene visualizzato utilizzando un <xref:System.Windows.Shapes.Path> elemento.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Triangolo creato con PathGeometry  
  
 Nell'esempio precedente è stato illustrato come creare una forma relativamente semplice, un triangolo. Un oggetto <xref:System.Windows.Media.PathGeometry> può essere usato anche per creare forme più complesse, tra cui archi e curve. Per esempi, vedere [creare un arco ellittico](how-to-create-an-elliptical-arc.md), [creare una curva di Bezier cubica](how-to-create-a-cubic-bezier-curve.md)e [creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md).  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
