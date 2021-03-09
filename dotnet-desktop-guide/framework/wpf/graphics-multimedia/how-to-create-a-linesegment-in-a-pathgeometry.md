---
title: 'Procedura: creare un oggetto LineSegment in un oggetto PathGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: c76772402bd54d2b835247352155150cdd443351
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511665"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="fc41f-102">Procedura: creare un oggetto LineSegment in un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="fc41f-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="fc41f-103">Questo esempio illustra come creare un segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="fc41f-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="fc41f-104">Per creare un segmento di linea, usare <xref:System.Windows.Media.PathGeometry> le <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.LineSegment> .</span><span class="sxs-lookup"><span data-stu-id="fc41f-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="fc41f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc41f-105">Example</span></span>

<span data-ttu-id="fc41f-106">Negli esempi seguenti viene disegnato un <xref:System.Windows.Media.LineSegment> da (10, 50) a (200, 70).</span><span class="sxs-lookup"><span data-stu-id="fc41f-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="fc41f-107">La figura seguente mostra l'oggetto risultante. <xref:System.Windows.Media.LineSegment> è stato aggiunto uno sfondo della griglia per mostrare il sistema di coordinate.</span><span class="sxs-lookup"><span data-stu-id="fc41f-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="fc41f-108">![Un LineSegment in un oggetto PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") LineSegment disegnato da (10, 50) a (200, 70)</span><span class="sxs-lookup"><span data-stu-id="fc41f-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="fc41f-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile usare la sintassi di attributo per descrivere un tracciato.</span><span class="sxs-lookup"><span data-stu-id="fc41f-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="fc41f-110">Si noti che questa sintassi di attributo crea effettivamente un oggetto <xref:System.Windows.Media.StreamGeometry> , una versione più leggera di un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="fc41f-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="fc41f-111">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="fc41f-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="fc41f-112">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile disegnare un segmento di linea usando la sintassi degli elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc41f-112">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="fc41f-113">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="fc41f-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="fc41f-114">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="fc41f-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc41f-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fc41f-115">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="fc41f-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="fc41f-116">Geometry Overview</span></span>](geometry-overview.md)
