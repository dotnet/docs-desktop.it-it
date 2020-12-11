---
title: 'Procedura: disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951258"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="d118d-102">Procedura: disegnare una linea</span><span class="sxs-lookup"><span data-stu-id="d118d-102">How to: Draw a Line</span></span>
<span data-ttu-id="d118d-103">Questo esempio illustra come creare linee usando l' <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="d118d-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="d118d-104">Per creare una linea, creare un <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="d118d-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="d118d-105">Usare le <xref:System.Windows.Shapes.Line.X1%2A> <xref:System.Windows.Shapes.Line.Y1%2A> proprietà e per impostarne il punto iniziale e usare le <xref:System.Windows.Shapes.Line.X2%2A> <xref:System.Windows.Shapes.Line.Y2%2A> proprietà e per impostarne il punto finale.</span><span class="sxs-lookup"><span data-stu-id="d118d-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="d118d-106">Infine, impostare la proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché una linea priva di un tratto è invisibile.</span><span class="sxs-lookup"><span data-stu-id="d118d-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="d118d-107">L'impostazione dell' <xref:System.Windows.Shapes.Shape.Fill%2A> elemento per una riga non ha alcun effetto, perché una linea non ha interni.</span><span class="sxs-lookup"><span data-stu-id="d118d-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="d118d-108">Nell'esempio seguente vengono disegnate tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="d118d-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d118d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d118d-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="d118d-110">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="d118d-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d118d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d118d-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="d118d-112">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="d118d-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
