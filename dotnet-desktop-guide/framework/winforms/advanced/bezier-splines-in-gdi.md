---
title: B&#233;spline Zier in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951562"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="338bb-102">B&#233;spline Zier in GDI+</span><span class="sxs-lookup"><span data-stu-id="338bb-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="338bb-103">Una spline di Bézier è una curva specificata da quattro punti: due punti finali (P1 e P2) e due punti di controllo (C1 e C2).</span><span class="sxs-lookup"><span data-stu-id="338bb-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="338bb-104">La curva inizia a P1 e termina in corrispondenza di P2.</span><span class="sxs-lookup"><span data-stu-id="338bb-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="338bb-105">La curva non passa attraverso i punti di controllo, ma i punti di controllo fungono da magneti, spostando la curva in determinate direzioni e influenzando il modo in cui la curva curva.</span><span class="sxs-lookup"><span data-stu-id="338bb-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="338bb-106">La figura seguente mostra una curva di Bézier insieme ai relativi endpoint e punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="338bb-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="338bb-107">![Spline di Bezier](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="338bb-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="338bb-108">La curva inizia da P1 e viene spostata verso il punto di controllo C1.</span><span class="sxs-lookup"><span data-stu-id="338bb-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="338bb-109">La linea tangente alla curva in P1 è la linea disegnata da P1 a C1.</span><span class="sxs-lookup"><span data-stu-id="338bb-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="338bb-110">La linea tangente nell'endpoint P2 è la linea disegnata da C2 a P2.</span><span class="sxs-lookup"><span data-stu-id="338bb-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="338bb-111">Disegno di spline Bézier</span><span class="sxs-lookup"><span data-stu-id="338bb-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="338bb-112">Per creare una spline di Bézier, è necessario disporre di un'istanza della <xref:System.Drawing.Graphics> classe e di un oggetto <xref:System.Drawing.Pen> .</span><span class="sxs-lookup"><span data-stu-id="338bb-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="338bb-113">L'istanza della <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawBezier%2A> metodo e <xref:System.Drawing.Pen> archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering della curva.</span><span class="sxs-lookup"><span data-stu-id="338bb-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="338bb-114"><xref:System.Drawing.Pen>Viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawBezier%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="338bb-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="338bb-115">Gli argomenti rimanenti passati al <xref:System.Drawing.Graphics.DrawBezier%2A> metodo sono gli endpoint e i punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="338bb-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="338bb-116">Nell'esempio seguente viene disegnata una spline Bézier con punto iniziale (0,0), punti di controllo (40, 20) e (80, 150) e punto finale (100, 10):</span><span class="sxs-lookup"><span data-stu-id="338bb-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="338bb-117">Nella figura seguente vengono illustrati la curva, i punti di controllo e due linee tangente.</span><span class="sxs-lookup"><span data-stu-id="338bb-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="338bb-118">![Spline di Bezier](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="338bb-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="338bb-119">Le spline di Bézier sono state originariamente sviluppate da Pierre Bézier per la progettazione nel settore automobilistico.</span><span class="sxs-lookup"><span data-stu-id="338bb-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="338bb-120">Poiché sono risultate utili in molti tipi di progettazione assistita da computer e vengono usati anche per definire le strutture dei tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="338bb-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="338bb-121">Le spline di Bézier possono produrre un'ampia gamma di forme, alcune delle quali sono illustrate nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="338bb-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="338bb-122">![Percorsi](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="338bb-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338bb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="338bb-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="338bb-124">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="338bb-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="338bb-125">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="338bb-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="338bb-126">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="338bb-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="338bb-127">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="338bb-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
