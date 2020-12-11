---
title: 'Procedura: creare una riga utilizzando un oggetto LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967330"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="5712b-102">Procedura: creare una riga utilizzando un oggetto LineGeometry</span><span class="sxs-lookup"><span data-stu-id="5712b-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="5712b-103">Questo esempio illustra come usare la <xref:System.Windows.Media.LineGeometry> classe per descrivere una riga.</span><span class="sxs-lookup"><span data-stu-id="5712b-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="5712b-104">Un <xref:System.Windows.Media.LineGeometry> viene definito dai relativi punti iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="5712b-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5712b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5712b-105">Example</span></span>  
 <span data-ttu-id="5712b-106">Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.LineGeometry> .</span><span class="sxs-lookup"><span data-stu-id="5712b-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="5712b-107"><xref:System.Windows.Shapes.Path>Viene usato un elemento per eseguire il rendering della riga.</span><span class="sxs-lookup"><span data-stu-id="5712b-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="5712b-108">Poiché una riga non ha un'area, l' <xref:System.Windows.Shapes.Path> oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> non è specificato, ma <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> vengono usate le proprietà e.</span><span class="sxs-lookup"><span data-stu-id="5712b-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="5712b-109">![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="5712b-109">![A LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="5712b-110">Un oggetto LineGeometry disegnato da (10,20) a (100,130)</span><span class="sxs-lookup"><span data-stu-id="5712b-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="5712b-111">Altre classi Geometry semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry> .</span><span class="sxs-lookup"><span data-stu-id="5712b-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="5712b-112">Queste geometrie, così come quelle più complesse, possono essere create anche usando <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry> .</span><span class="sxs-lookup"><span data-stu-id="5712b-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="5712b-113">Per altre informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5712b-113">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5712b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5712b-114">See also</span></span>

- [<span data-ttu-id="5712b-115">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="5712b-115">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="5712b-116">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="5712b-116">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="5712b-117">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="5712b-117">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
