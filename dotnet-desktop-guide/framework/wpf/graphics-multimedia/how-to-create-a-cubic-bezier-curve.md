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
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="99725-102">Procedura: creare una curva di Bezier cubica</span><span class="sxs-lookup"><span data-stu-id="99725-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="99725-103">Questo esempio illustra come creare una curva di Bezier cubica.</span><span class="sxs-lookup"><span data-stu-id="99725-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="99725-104">Per creare una curva di Bezier cubica, usare le <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.BezierSegment> .</span><span class="sxs-lookup"><span data-stu-id="99725-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="99725-105">Per visualizzare la geometria risultante, utilizzare un <xref:System.Windows.Shapes.Path> elemento o utilizzarlo con un oggetto <xref:System.Windows.Media.GeometryDrawing> o un oggetto <xref:System.Windows.Media.DrawingContext> .</span><span class="sxs-lookup"><span data-stu-id="99725-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="99725-106">Negli esempi seguenti viene disegnata una curva di Bezier cubica da (10, 100) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="99725-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="99725-107">La curva ha punti di controllo di (100, 0) e (200, 200).</span><span class="sxs-lookup"><span data-stu-id="99725-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99725-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="99725-108">Example</span></span>  

 <span data-ttu-id="99725-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare la sintassi di markup abbreviata per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="99725-109">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]
  
 <span data-ttu-id="99725-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile creare una curva di Bezier cubica usando i tag Object.</span><span class="sxs-lookup"><span data-stu-id="99725-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="99725-111">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="99725-111">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="99725-112">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="99725-112">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99725-113">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="99725-113">See also</span></span>

- [<span data-ttu-id="99725-114">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="99725-114">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="99725-115">Creare un oggetto LineSegment in un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="99725-115">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="99725-116">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="99725-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="99725-117">Creare una curva di Bézier quadratica</span><span class="sxs-lookup"><span data-stu-id="99725-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
