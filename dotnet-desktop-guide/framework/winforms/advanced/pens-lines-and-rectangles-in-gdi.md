---
title: Penne, linee e rettangoli in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963112"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="b0862-102">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="b0862-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="b0862-103">Per creare linee con GDI+ è necessario creare un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0862-103">To draw lines with GDI+ you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b0862-104">L' <xref:System.Drawing.Graphics> oggetto fornisce i metodi che eseguono effettivamente il disegno e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio il colore, la larghezza e lo stile della linea.</span><span class="sxs-lookup"><span data-stu-id="b0862-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="b0862-105">Disegno di una linea</span><span class="sxs-lookup"><span data-stu-id="b0862-105">Drawing a Line</span></span>  
 <span data-ttu-id="b0862-106">Per creare una linea, chiamare il <xref:System.Drawing.Graphics.DrawLine%2A> metodo dell' <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0862-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b0862-107">L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawLine%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b0862-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="b0862-108">Nell'esempio seguente viene disegnata una riga dal punto (4, 2) al punto (12, 6):</span><span class="sxs-lookup"><span data-stu-id="b0862-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="b0862-109"><xref:System.Drawing.Graphics.DrawLine%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="b0862-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="b0862-110">È ad esempio possibile costruire due <xref:System.Drawing.Point> oggetti e passare gli <xref:System.Drawing.Point> oggetti come argomenti al <xref:System.Drawing.Graphics.DrawLine%2A> Metodo:</span><span class="sxs-lookup"><span data-stu-id="b0862-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="b0862-111">Creazione di una penna</span><span class="sxs-lookup"><span data-stu-id="b0862-111">Constructing a Pen</span></span>  
 <span data-ttu-id="b0862-112">È possibile specificare determinati attributi quando si costruisce un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0862-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b0862-113">Un costruttore, ad esempio, `Pen` consente di specificare il colore e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="b0862-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="b0862-114">Nell'esempio seguente viene disegnata una linea blu di larghezza 2 da (0,0) a (60, 30):</span><span class="sxs-lookup"><span data-stu-id="b0862-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="b0862-115">Linee tratteggiate e estremità di linea</span><span class="sxs-lookup"><span data-stu-id="b0862-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="b0862-116">L' <xref:System.Drawing.Pen> oggetto espone anche proprietà, ad esempio <xref:System.Drawing.Pen.DashStyle%2A> , che è possibile usare per specificare le funzionalità della riga.</span><span class="sxs-lookup"><span data-stu-id="b0862-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="b0862-117">Nell'esempio seguente viene disegnata una linea tratteggiata da (100, 50) a (300, 80):</span><span class="sxs-lookup"><span data-stu-id="b0862-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="b0862-118">È possibile utilizzare le proprietà dell' <xref:System.Drawing.Pen> oggetto per impostare molti più attributi della riga.</span><span class="sxs-lookup"><span data-stu-id="b0862-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="b0862-119">Le <xref:System.Drawing.Pen.StartCap%2A> <xref:System.Drawing.Pen.EndCap%2A> proprietà e specificano l'aspetto delle estremità della linea; le estremità possono essere flat, Square, arrotondate, triangolari o una forma personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b0862-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="b0862-120">La <xref:System.Drawing.Pen.LineJoin%2A> proprietà consente di specificare se le linee connesse sono sgolato (unite a angoli acuti), smussate, arrotondate o ritagliate.</span><span class="sxs-lookup"><span data-stu-id="b0862-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="b0862-121">Nella figura seguente sono illustrate le righe con diversi stili di terminazione e di join.</span><span class="sxs-lookup"><span data-stu-id="b0862-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="b0862-122">![Linee](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="b0862-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="b0862-123">Disegno di un rettangolo</span><span class="sxs-lookup"><span data-stu-id="b0862-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="b0862-124">Il disegno di rettangoli con GDI+ è simile a quello delle linee di disegno.</span><span class="sxs-lookup"><span data-stu-id="b0862-124">Drawing rectangles with GDI+ is similar to drawing lines.</span></span> <span data-ttu-id="b0862-125">Per creare un rettangolo, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0862-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b0862-126">L' <xref:System.Drawing.Graphics> oggetto fornisce un <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la lunghezza della linea e il colore.</span><span class="sxs-lookup"><span data-stu-id="b0862-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="b0862-127">L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b0862-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="b0862-128">Nell'esempio seguente viene disegnato un rettangolo con il relativo angolo superiore sinistro in (100, 50), una larghezza di 80 e un'altezza pari a 40:</span><span class="sxs-lookup"><span data-stu-id="b0862-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="b0862-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="b0862-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="b0862-130">È ad esempio possibile costruire un <xref:System.Drawing.Rectangle> oggetto e passare l' <xref:System.Drawing.Rectangle> oggetto al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo come argomento:</span><span class="sxs-lookup"><span data-stu-id="b0862-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="b0862-131">Un <xref:System.Drawing.Rectangle> oggetto dispone di metodi e proprietà per la modifica e la raccolta di informazioni sul rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b0862-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="b0862-132">Ad esempio, i <xref:System.Drawing.Rectangle.Inflate%2A> <xref:System.Drawing.Rectangle.Offset%2A> metodi e modificano le dimensioni e la posizione del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b0862-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="b0862-133">Il <xref:System.Drawing.Rectangle.IntersectsWith%2A> metodo indica se il rettangolo interseca un altro rettangolo specificato e il <xref:System.Drawing.Rectangle.Contains%2A> metodo indica se un punto specificato si trova all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b0862-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0862-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0862-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="b0862-135">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="b0862-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="b0862-136">Procedura: Disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="b0862-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="b0862-137">Procedura: Disegnare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="b0862-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
