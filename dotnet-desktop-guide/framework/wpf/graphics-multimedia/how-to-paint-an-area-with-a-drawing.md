---
title: "Procedura: inserire un disegno in un'area"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969853"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="a10b1-102">Procedura: inserire un disegno in un'area</span><span class="sxs-lookup"><span data-stu-id="a10b1-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="a10b1-103">Questo esempio spiega come inserire un disegno in un'area.</span><span class="sxs-lookup"><span data-stu-id="a10b1-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="a10b1-104">Per disegnare un'area con un disegno, usare un oggetto <xref:System.Windows.Media.DrawingBrush> e uno o più <xref:System.Windows.Media.Drawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="a10b1-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="a10b1-105">Nell'esempio seguente viene usato un <xref:System.Windows.Media.DrawingBrush> oggetto per disegnare un oggetto con un disegno di due ellissi.</span><span class="sxs-lookup"><span data-stu-id="a10b1-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a10b1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a10b1-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="a10b1-107">L'immagine seguente illustra l'output dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="a10b1-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="a10b1-108">![Output di DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="a10b1-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="a10b1-109">Il centro della forma è bianco per i motivi descritti in     [controllare il riempimento di una forma composta](how-to-control-the-fill-of-a-composite-shape.md).</span><span class="sxs-lookup"><span data-stu-id="a10b1-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="a10b1-110">Impostando <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.TileBrush.Viewport%2A> le proprietà e di un oggetto <xref:System.Windows.Media.TileBrush.TileMode%2A> , è possibile creare un modello ripetuto.</span><span class="sxs-lookup"><span data-stu-id="a10b1-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="a10b1-111">L'esempio seguente disegna un oggetto con un motivo creato da un disegno di due ellissi.</span><span class="sxs-lookup"><span data-stu-id="a10b1-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="a10b1-112">Nella figura seguente viene illustrato l' <xref:System.Windows.Media.DrawingBrush> output affiancato.</span><span class="sxs-lookup"><span data-stu-id="a10b1-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="a10b1-113">![Output affiancato di DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="a10b1-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="a10b1-114">Per altre informazioni sulla creazione di pennelli, vedere disegnare [con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="a10b1-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="a10b1-115">Per ulteriori informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a10b1-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
