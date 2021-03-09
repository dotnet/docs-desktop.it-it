---
title: 'Procedura: creare un arco ellittico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 4963b671e07255053aef3661a0f7675ef6c5b69f
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511645"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="6d8fe-102">Procedura: creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="6d8fe-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="6d8fe-103">Questo esempio illustra come creare un arco ellittico. Per creare un arco ellittico, usare le <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.ArcSegment> .</span><span class="sxs-lookup"><span data-stu-id="6d8fe-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d8fe-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d8fe-104">Example</span></span>  
 <span data-ttu-id="6d8fe-105">Negli esempi seguenti viene disegnato un arco ellittico da (10.100) a (200.100).</span><span class="sxs-lookup"><span data-stu-id="6d8fe-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="6d8fe-106">L'arco ha un <xref:System.Windows.Media.ArcSegment.Size%2A> valore di 100 di 50 pixel indipendenti dal dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> di 45 gradi, un' <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> impostazione di `true` e un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> di <xref:System.Windows.Media.SweepDirection.Counterclockwise> .</span><span class="sxs-lookup"><span data-stu-id="6d8fe-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  

 <span data-ttu-id="6d8fe-107">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare la sintassi degli attributi per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="6d8fe-107">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  

 <span data-ttu-id="6d8fe-108">Si noti che questa sintassi di attributo crea effettivamente un oggetto <xref:System.Windows.Media.StreamGeometry> , una versione più leggera di un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="6d8fe-108">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="6d8fe-109">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="6d8fe-109">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="6d8fe-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile creare un arco ellittico usando in modo esplicito i tag Object.</span><span class="sxs-lookup"><span data-stu-id="6d8fe-110">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="6d8fe-111">Il codice seguente equivale al markup precedente [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d8fe-111">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="6d8fe-112">Questo esempio fa parte di un esempio più esaustivo.</span><span class="sxs-lookup"><span data-stu-id="6d8fe-112">This example is part of a larger sample.</span></span> <span data-ttu-id="6d8fe-113">Per l'esempio completo, vedere l' [esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="6d8fe-113">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d8fe-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6d8fe-114">See also</span></span>

- [<span data-ttu-id="6d8fe-115">Creare una curva di Bézier quadratica</span><span class="sxs-lookup"><span data-stu-id="6d8fe-115">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="6d8fe-116">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="6d8fe-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
