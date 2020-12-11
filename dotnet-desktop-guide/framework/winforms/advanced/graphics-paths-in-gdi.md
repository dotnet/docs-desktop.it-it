---
title: Percorsi di oggetti Graphics in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951511"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="4f9c3-102">Percorsi di oggetti Graphics in GDI+</span><span class="sxs-lookup"><span data-stu-id="4f9c3-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="4f9c3-103">I percorsi vengono formati combinando linee, rettangoli e curve semplici.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="4f9c3-104">Dal Panoramica della [grafica vettoriale](vector-graphics-overview.md) , i blocchi predefiniti di base seguenti si sono dimostrati più utili per il disegno di immagini:</span><span class="sxs-lookup"><span data-stu-id="4f9c3-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="4f9c3-105">Linee</span><span class="sxs-lookup"><span data-stu-id="4f9c3-105">Lines</span></span>  
  
- <span data-ttu-id="4f9c3-106">Rettangoli</span><span class="sxs-lookup"><span data-stu-id="4f9c3-106">Rectangles</span></span>  
  
- <span data-ttu-id="4f9c3-107">Ellissi</span><span class="sxs-lookup"><span data-stu-id="4f9c3-107">Ellipses</span></span>  
  
- <span data-ttu-id="4f9c3-108">Archi</span><span class="sxs-lookup"><span data-stu-id="4f9c3-108">Arcs</span></span>  
  
- <span data-ttu-id="4f9c3-109">Poligoni</span><span class="sxs-lookup"><span data-stu-id="4f9c3-109">Polygons</span></span>  
  
- <span data-ttu-id="4f9c3-110">Spline cardinali</span><span class="sxs-lookup"><span data-stu-id="4f9c3-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="4f9c3-111">Spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="4f9c3-111">Bézier splines</span></span>  
  
 <span data-ttu-id="4f9c3-112">In GDI+ l' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di questi blocchi predefiniti in un'unica unità.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="4f9c3-113">L'intera sequenza di linee, rettangoli, poligoni e curve può quindi essere disegnata con una chiamata al <xref:System.Drawing.Graphics.DrawPath%2A> metodo della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4f9c3-114">Nella figura seguente viene illustrato un percorso creato combinando una linea, un arco, una spline di Bézier e una spline di cardinalità.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="4f9c3-115">![Percorso](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="4f9c3-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="4f9c3-116">Uso di un percorso</span><span class="sxs-lookup"><span data-stu-id="4f9c3-116">Using a Path</span></span>  
 <span data-ttu-id="4f9c3-117">La <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da disegnare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> ,, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per le spline cardinalhe) e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> .</span><span class="sxs-lookup"><span data-stu-id="4f9c3-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="4f9c3-118">Ognuno di questi metodi è sovraccarico; ovvero, ogni metodo supporta diversi elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="4f9c3-119">Ad esempio, una variante del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro numeri interi e un'altra variante del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="4f9c3-120">I metodi per aggiungere linee, rettangoli e spline di Bézier a un percorso hanno metodi complementari plurali che aggiungono più elementi al percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> .</span><span class="sxs-lookup"><span data-stu-id="4f9c3-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="4f9c3-121">Inoltre, i <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi e hanno metodi complementari, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> , che aggiungono una curva o una torta chiusa al percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="4f9c3-122">Per tracciare un percorso, sono necessari un <xref:System.Drawing.Graphics> oggetto, un oggetto <xref:System.Drawing.Pen> e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="4f9c3-123">L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPath%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering del percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="4f9c3-124">L' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="4f9c3-125">L' <xref:System.Drawing.Pen> oggetto e l' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti al <xref:System.Drawing.Graphics.DrawPath%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="4f9c3-126">Nell'esempio seguente viene disegnato un percorso costituito da una linea, un'ellisse e una spline di Bézier:</span><span class="sxs-lookup"><span data-stu-id="4f9c3-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="4f9c3-127">Nella figura seguente viene illustrato il percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="4f9c3-128">![Percorso](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="4f9c3-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="4f9c3-129">Oltre ad aggiungere linee, rettangoli e curve a un tracciato, è possibile aggiungere percorsi a un percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="4f9c3-130">In questo modo è possibile combinare i percorsi esistenti per formare percorsi complessi e di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="4f9c3-131">Esistono altri due elementi che è possibile aggiungere a un percorso: stringhe e torte.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="4f9c3-132">Una torta è una parte dell'area interna di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="4f9c3-133">Nell'esempio seguente viene creato un percorso da un arco, una spline Cardinal, una stringa e una torta:</span><span class="sxs-lookup"><span data-stu-id="4f9c3-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="4f9c3-134">Nella figura seguente viene illustrato il percorso.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-134">The following illustration shows the path.</span></span> <span data-ttu-id="4f9c3-135">Si noti che non è necessario che un percorso sia connesso; l'arco, la spline di cardinalità, la stringa e la torta sono separate.</span><span class="sxs-lookup"><span data-stu-id="4f9c3-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="4f9c3-136">![Percorsi](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="4f9c3-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9c3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f9c3-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="4f9c3-138">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="4f9c3-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="4f9c3-139">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="4f9c3-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="4f9c3-140">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="4f9c3-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
