---
title: 'Procedura: creare una singola Zier B&#233;spline'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962710"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="99b28-102">Procedura: creare una singola Zier B&#233;spline</span><span class="sxs-lookup"><span data-stu-id="99b28-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="99b28-103">Una spline Bézier è definita da quattro punti: un punto iniziale, due punti di controllo e un endpoint.</span><span class="sxs-lookup"><span data-stu-id="99b28-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b28-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="99b28-104">Example</span></span>  
 <span data-ttu-id="99b28-105">Nell'esempio seguente viene disegnata una spline Bézier con il punto iniziale (10, 100) e l'endpoint (200, 100).</span><span class="sxs-lookup"><span data-stu-id="99b28-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="99b28-106">I punti di controllo sono (100, 10) e (150, 150).</span><span class="sxs-lookup"><span data-stu-id="99b28-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="99b28-107">Nell'illustrazione seguente viene mostrata la spline di Bézier risultante insieme al punto iniziale, ai punti di controllo e all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="99b28-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="99b28-108">L'illustrazione mostra anche la struttura convessa della spline, ovvero un poligono formato dalla connessione dei quattro punti con linee rette.</span><span class="sxs-lookup"><span data-stu-id="99b28-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Illustrazione di una spline di Bezier.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99b28-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="99b28-110">Compiling the Code</span></span>  
 <span data-ttu-id="99b28-111">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="99b28-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b28-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99b28-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="99b28-113">Spline di Bézier in GDI+</span><span class="sxs-lookup"><span data-stu-id="99b28-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="99b28-114">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="99b28-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
