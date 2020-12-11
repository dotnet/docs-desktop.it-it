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
# <a name="how-to-draw-cardinal-splines"></a>Procedura: Disegnare cardinal spline
Una spline di cardinalità è una curva che passa in modo uniforme attraverso un set di punti specificato. Per creare una spline di cardinalità, creare un <xref:System.Drawing.Graphics> oggetto e passare l'indirizzo di una matrice di punti al <xref:System.Drawing.Graphics.DrawCurve%2A> metodo.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Disegno di una spline di Bell-Shaped Cardinal  
  
- Nell'esempio seguente viene disegnata una spline di cardinalità a forma di campana che passa attraverso cinque punti designati. Nella figura seguente vengono illustrati la curva e cinque punti.  
  
     ![Diagramma che mostra una spline cardinala a forma di campana.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Disegno di una spline di Cardinal chiusa  
  
- Usare il <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo della <xref:System.Drawing.Graphics> classe per creare una spline Cardinal chiusa. In una spline di Cardinal chiusa la curva continua fino all'ultimo punto nella matrice e si connette con il primo punto nella matrice. Nell'esempio seguente viene disegnata una spline di Cardinal chiusa che passa attraverso sei punti designati. Nella figura seguente viene illustrata la spline chiusa insieme ai sei punti:  
  
 ![Diagramma che mostra una spline Cardinal chiusa.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Modifica della curva di una spline Cardinal  
  
- Modificare la curva di una spline di tipo Cardinal passando un argomento di tensionamento al <xref:System.Drawing.Graphics.DrawCurve%2A> metodo. Nell'esempio seguente vengono disegnate tre spline cardinali che passano attraverso lo stesso set di punti. Nella figura seguente sono illustrate le tre spline insieme ai relativi valori di tensione. Si noti che quando la tensione è 0, i punti sono collegati da linee rette.  
  
 ![Diagramma che mostra tre spline cardinali.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
