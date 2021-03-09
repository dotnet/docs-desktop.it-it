---
title: 'Procedura: creare una curva di Bezier quadratica'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: c74963069f45666798d2201533591745f3c0f7b2
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511632"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="e13b6-102">Procedura: creare una curva di Bezier quadratica</span><span class="sxs-lookup"><span data-stu-id="e13b6-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="e13b6-103">Questo esempio illustra come creare una curva di Bézier quadratica.</span><span class="sxs-lookup"><span data-stu-id="e13b6-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="e13b6-104">Per creare una curva di Bézier quadratica, usare <xref:System.Windows.Media.PathGeometry> le <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.QuadraticBezierSegment> .</span><span class="sxs-lookup"><span data-stu-id="e13b6-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e13b6-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e13b6-105">Example</span></span>  
 <span data-ttu-id="e13b6-106">Negli esempi seguenti viene disegnata una curva di Bézier quadratica da (10.100) a (300.100).</span><span class="sxs-lookup"><span data-stu-id="e13b6-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="e13b6-107">La curva dispone di un punto di controllo di (200.200).</span><span class="sxs-lookup"><span data-stu-id="e13b6-107">The curve has a control point of (200,200).</span></span>  

 <span data-ttu-id="e13b6-108">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare la sintassi degli attributi per descrivere un percorso.</span><span class="sxs-lookup"><span data-stu-id="e13b6-108">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  

 <span data-ttu-id="e13b6-109">Si noti che questa sintassi di attributo crea effettivamente un oggetto <xref:System.Windows.Media.StreamGeometry> , una versione più leggera di un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="e13b6-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="e13b6-110">Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="e13b6-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="e13b6-111">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile creare una curva di Bézier quadratica usando la sintassi dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="e13b6-111">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="e13b6-112">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="e13b6-112">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="e13b6-113">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="e13b6-113">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13b6-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e13b6-114">See also</span></span>

- [<span data-ttu-id="e13b6-115">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="e13b6-115">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="e13b6-116">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="e13b6-116">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
