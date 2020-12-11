---
title: 'Procedura: creare una forma composta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967987"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="405e2-102">Procedura: creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="405e2-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="405e2-103">In questo esempio viene illustrato come creare forme composite utilizzando <xref:System.Windows.Media.Geometry> oggetti e visualizzarle utilizzando un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="405e2-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="405e2-104">Nell'esempio seguente, un oggetto <xref:System.Windows.Media.LineGeometry> , <xref:System.Windows.Media.EllipseGeometry> e un oggetto <xref:System.Windows.Media.RectangleGeometry> vengono utilizzati con un oggetto <xref:System.Windows.Media.GeometryGroup> per creare una forma composta.</span><span class="sxs-lookup"><span data-stu-id="405e2-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="405e2-105">Le geometrie vengono quindi disegnate utilizzando un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="405e2-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="405e2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="405e2-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="405e2-107">La figura seguente mostra la forma creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="405e2-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="405e2-108">![Geometria composta creata con GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="405e2-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="405e2-109">Geometria composita</span><span class="sxs-lookup"><span data-stu-id="405e2-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="405e2-110">È possibile creare forme più complesse, ad esempio poligoni e forme con segmenti curvi, usando <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="405e2-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="405e2-111">Per un esempio che illustra come creare una forma usando un oggetto <xref:System.Windows.Media.PathGeometry> , vedere [creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="405e2-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="405e2-112">Sebbene in questo esempio venga eseguito il rendering di una forma sullo schermo utilizzando un <xref:System.Windows.Shapes.Path> elemento, <xref:System.Windows.Media.Geometry> gli oggetti possono essere utilizzati anche per descrivere il contenuto di un oggetto <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext> .</span><span class="sxs-lookup"><span data-stu-id="405e2-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="405e2-113">Possono anche essere usati per il ritaglio e l'hit testing.</span><span class="sxs-lookup"><span data-stu-id="405e2-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="405e2-114">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="405e2-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
