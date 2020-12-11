---
title: 'Procedura: disegnare un rettangolo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951590"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="c44bd-102">Procedura: disegnare un rettangolo</span><span class="sxs-lookup"><span data-stu-id="c44bd-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="c44bd-103">Questo esempio illustra come creare un rettangolo usando l' <xref:System.Windows.Shapes.Rectangle> elemento.</span><span class="sxs-lookup"><span data-stu-id="c44bd-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="c44bd-104">Per creare un rettangolo, creare un <xref:System.Windows.Shapes.Rectangle> elemento e specificare i relativi <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="c44bd-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="c44bd-105">Per disegnare l'interno del rettangolo, impostarne il relativo oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> .</span><span class="sxs-lookup"><span data-stu-id="c44bd-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="c44bd-106">Per assegnare un contorno al rettangolo, utilizzare <xref:System.Windows.Shapes.Shape.Stroke%2A> le <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà e.</span><span class="sxs-lookup"><span data-stu-id="c44bd-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="c44bd-107">Per assegnare gli angoli arrotondati al rettangolo, specificare le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> proprietà e facoltative <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> .</span><span class="sxs-lookup"><span data-stu-id="c44bd-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="c44bd-108">Le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà e consentono di impostare l'asse x e il raggio dell'asse y dell'ellisse utilizzata per arrotondare gli angoli del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="c44bd-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="c44bd-109">Nell'esempio seguente <xref:System.Windows.Shapes.Rectangle> vengono disegnati due elementi in un oggetto <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="c44bd-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c44bd-110">Il primo rettangolo ha una parte <xref:System.Windows.Media.Brushes.Blue%2A> interna.</span><span class="sxs-lookup"><span data-stu-id="c44bd-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="c44bd-111">Il secondo rettangolo ha una parte <xref:System.Windows.Media.Brushes.Blue%2A> interna, una <xref:System.Windows.Media.Brushes.Black%2A> struttura e gli angoli arrotondati.</span><span class="sxs-lookup"><span data-stu-id="c44bd-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c44bd-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c44bd-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="c44bd-113">Sebbene in questo esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere i rettangoli, è possibile utilizzare gli elementi Rectangle (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="c44bd-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="c44bd-114">Infatti, i rettangoli sono particolarmente utili per fornire sfondi per parti di <xref:System.Windows.Controls.Grid> pannelli.</span><span class="sxs-lookup"><span data-stu-id="c44bd-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="c44bd-115">Per un esempio, vedere [Panoramica della tabella](../advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c44bd-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="c44bd-116">Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="c44bd-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44bd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c44bd-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="c44bd-118">Esempio di elementi Shape</span><span class="sxs-lookup"><span data-stu-id="c44bd-118">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="c44bd-119">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="c44bd-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="c44bd-120">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="c44bd-120">Table Overview</span></span>](../advanced/table-overview.md)
