---
title: Poligoni in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952817"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="f3611-102">Poligoni in GDI+</span><span class="sxs-lookup"><span data-stu-id="f3611-102">Polygons in GDI+</span></span>
<span data-ttu-id="f3611-103">Un poligono è una forma chiusa con tre o più lati dritti.</span><span class="sxs-lookup"><span data-stu-id="f3611-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="f3611-104">Ad esempio, un triangolo è un poligono con tre lati, un rettangolo è un poligono con quattro lati e un pentagono è un poligono con cinque lati.</span><span class="sxs-lookup"><span data-stu-id="f3611-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="f3611-105">Nella figura seguente vengono illustrati diversi poligoni.</span><span class="sxs-lookup"><span data-stu-id="f3611-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="f3611-106">![Poligoni](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="f3611-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="f3611-107">Disegno di un poligono</span><span class="sxs-lookup"><span data-stu-id="f3611-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="f3611-108">Per creare un poligono, sono necessari un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> oggetto e una matrice di <xref:System.Drawing.Point> oggetti (o <xref:System.Drawing.PointF> ).</span><span class="sxs-lookup"><span data-stu-id="f3611-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="f3611-109">L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f3611-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="f3611-110">L' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per eseguire il rendering del poligono e la matrice di <xref:System.Drawing.Point> oggetti archivia i punti da connettere tramite linee rette.</span><span class="sxs-lookup"><span data-stu-id="f3611-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="f3611-111">L' <xref:System.Drawing.Pen> oggetto e la matrice di <xref:System.Drawing.Point> oggetti vengono passati come argomenti al <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f3611-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="f3611-112">Nell'esempio seguente viene disegnato un poligono a tre facce.</span><span class="sxs-lookup"><span data-stu-id="f3611-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="f3611-113">Si noti che sono presenti solo tre punti in `myPointArray` : (0, 0), (50, 30) e (30, 60).</span><span class="sxs-lookup"><span data-stu-id="f3611-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="f3611-114">Il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo chiude automaticamente il poligono disegnando una riga da (30, 60) al punto iniziale (0, 0).</span><span class="sxs-lookup"><span data-stu-id="f3611-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="f3611-115">Nella figura seguente viene illustrato il poligono.</span><span class="sxs-lookup"><span data-stu-id="f3611-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="f3611-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="f3611-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3611-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3611-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="f3611-118">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="f3611-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f3611-119">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="f3611-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
