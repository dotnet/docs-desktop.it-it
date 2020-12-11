---
title: Ellissi e archi in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960691"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="5f784-102">Ellissi e archi in GDI+</span><span class="sxs-lookup"><span data-stu-id="5f784-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="5f784-103">È possibile creare facilmente ellissi e archi usando i <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> metodi e della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="5f784-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="5f784-104">Disegno di un'ellisse</span><span class="sxs-lookup"><span data-stu-id="5f784-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="5f784-105">Per creare un'ellisse, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5f784-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5f784-106">L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering dell'ellisse.</span><span class="sxs-lookup"><span data-stu-id="5f784-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="5f784-107">L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="5f784-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="5f784-108">Gli argomenti rimanenti passati al <xref:System.Drawing.Graphics.DrawEllipse%2A> Metodo specificano il rettangolo di delimitazione per l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="5f784-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="5f784-109">Nell'illustrazione seguente viene mostrata un'ellisse insieme al rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="5f784-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="5f784-110">![Ellissi e archi](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="5f784-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="5f784-111">Nell'esempio seguente viene disegnata un'ellisse. il rettangolo di delimitazione ha una larghezza di 80, un'altezza di 40 e un angolo superiore sinistro di (100, 50):</span><span class="sxs-lookup"><span data-stu-id="5f784-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="5f784-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="5f784-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="5f784-113">È ad esempio possibile costruire un oggetto <xref:System.Drawing.Rectangle> e passare al <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo come argomento:</span><span class="sxs-lookup"><span data-stu-id="5f784-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="5f784-114">Disegno di un arco</span><span class="sxs-lookup"><span data-stu-id="5f784-114">Drawing an Arc</span></span>  
 <span data-ttu-id="5f784-115">Un arco è una parte di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="5f784-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="5f784-116">Per creare un arco, chiamare il <xref:System.Drawing.Graphics.DrawArc%2A> metodo della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="5f784-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="5f784-117">I parametri del <xref:System.Drawing.Graphics.DrawArc%2A> metodo sono gli stessi dei parametri del <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo, ad eccezione del fatto che <xref:System.Drawing.Graphics.DrawArc%2A> richiede un angolo iniziale e un angolo di apertura.</span><span class="sxs-lookup"><span data-stu-id="5f784-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="5f784-118">Nell'esempio seguente viene disegnato un arco con un angolo iniziale di 30 gradi e un angolo di apertura di 180 gradi:</span><span class="sxs-lookup"><span data-stu-id="5f784-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="5f784-119">Nella figura seguente vengono illustrati l'arco, l'ellisse e il rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="5f784-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="5f784-120">![Ellissi e archi](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="5f784-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f784-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f784-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="5f784-122">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="5f784-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5f784-123">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="5f784-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="5f784-124">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="5f784-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="5f784-125">Procedura: Disegnare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="5f784-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
