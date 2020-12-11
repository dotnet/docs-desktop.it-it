---
title: 'Procedura: Disegnare cardinal spline'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 12e938567d529b33ead93e081d380a650a803f23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962680"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="934ed-102">Procedura: Disegnare cardinal spline</span><span class="sxs-lookup"><span data-stu-id="934ed-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="934ed-103">Una spline di cardinalità è una curva che passa in modo uniforme attraverso un set di punti specificato.</span><span class="sxs-lookup"><span data-stu-id="934ed-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="934ed-104">Per creare una spline di cardinalità, creare un <xref:System.Drawing.Graphics> oggetto e passare l'indirizzo di una matrice di punti al <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="934ed-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="934ed-105">Disegno di una spline di Bell-Shaped Cardinal</span><span class="sxs-lookup"><span data-stu-id="934ed-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
- <span data-ttu-id="934ed-106">Nell'esempio seguente viene disegnata una spline di cardinalità a forma di campana che passa attraverso cinque punti designati.</span><span class="sxs-lookup"><span data-stu-id="934ed-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="934ed-107">Nella figura seguente vengono illustrati la curva e cinque punti.</span><span class="sxs-lookup"><span data-stu-id="934ed-107">The following illustration shows the curve and five points.</span></span>  
  
     ![Diagramma che mostra una spline cardinala a forma di campana.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="934ed-109">Disegno di una spline di Cardinal chiusa</span><span class="sxs-lookup"><span data-stu-id="934ed-109">Drawing a Closed Cardinal Spline</span></span>  
  
- <span data-ttu-id="934ed-110">Usare il <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo della <xref:System.Drawing.Graphics> classe per creare una spline Cardinal chiusa.</span><span class="sxs-lookup"><span data-stu-id="934ed-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="934ed-111">In una spline di Cardinal chiusa la curva continua fino all'ultimo punto nella matrice e si connette con il primo punto nella matrice.</span><span class="sxs-lookup"><span data-stu-id="934ed-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="934ed-112">Nell'esempio seguente viene disegnata una spline di Cardinal chiusa che passa attraverso sei punti designati.</span><span class="sxs-lookup"><span data-stu-id="934ed-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="934ed-113">Nella figura seguente viene illustrata la spline chiusa insieme ai sei punti:</span><span class="sxs-lookup"><span data-stu-id="934ed-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![Diagramma che mostra una spline Cardinal chiusa.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="934ed-115">Modifica della curva di una spline Cardinal</span><span class="sxs-lookup"><span data-stu-id="934ed-115">Changing the Bend of a Cardinal Spline</span></span>  
  
- <span data-ttu-id="934ed-116">Modificare la curva di una spline di tipo Cardinal passando un argomento di tensionamento al <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="934ed-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="934ed-117">Nell'esempio seguente vengono disegnate tre spline cardinali che passano attraverso lo stesso set di punti.</span><span class="sxs-lookup"><span data-stu-id="934ed-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="934ed-118">Nella figura seguente sono illustrate le tre spline insieme ai relativi valori di tensione.</span><span class="sxs-lookup"><span data-stu-id="934ed-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="934ed-119">Si noti che quando la tensione è 0, i punti sono collegati da linee rette.</span><span class="sxs-lookup"><span data-stu-id="934ed-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![Diagramma che mostra tre spline cardinali.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="934ed-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="934ed-121">Compiling the Code</span></span>  
 <span data-ttu-id="934ed-122">Gli esempi precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="934ed-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934ed-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="934ed-123">See also</span></span>

- [<span data-ttu-id="934ed-124">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="934ed-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="934ed-125">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="934ed-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
