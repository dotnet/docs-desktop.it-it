---
title: 'Procedura: modificare la terminazione alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969871"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="b2063-102">Procedura: modificare la terminazione alla fine di una linea o di un segmento</span><span class="sxs-lookup"><span data-stu-id="b2063-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="b2063-103">Questo esempio illustra come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> .</span><span class="sxs-lookup"><span data-stu-id="b2063-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="b2063-104">Per modificare la terminazione all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape> , utilizzare la relativa <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2063-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="b2063-105">Per modificare la terminazione alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape> , utilizzare la relativa <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2063-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="b2063-106">Per visualizzare i limiti di riga disponibili, vedere l' <xref:System.Windows.Media.PenLineCap> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b2063-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2063-107">Questa proprietà ha effetto solo su una forma aperta, ad esempio un oggetto <xref:System.Windows.Shapes.Line> , un oggetto <xref:System.Windows.Shapes.Polyline> o un <xref:System.Windows.Shapes.Path> elemento aperto.</span><span class="sxs-lookup"><span data-stu-id="b2063-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="b2063-108">Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set di forme diverso alle estremità di ogni.</span><span class="sxs-lookup"><span data-stu-id="b2063-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2063-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2063-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="b2063-110">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="b2063-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2063-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2063-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
