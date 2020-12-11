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
# <a name="how-to-draw-a-single-b233zier-spline"></a>Procedura: creare una singola Zier B&#233;spline
Una spline Bézier è definita da quattro punti: un punto iniziale, due punti di controllo e un endpoint.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnata una spline Bézier con il punto iniziale (10, 100) e l'endpoint (200, 100). I punti di controllo sono (100, 10) e (150, 150).  
  
 Nell'illustrazione seguente viene mostrata la spline di Bézier risultante insieme al punto iniziale, ai punti di controllo e all'endpoint. L'illustrazione mostra anche la struttura convessa della spline, ovvero un poligono formato dalla connessione dei quattro punti con linee rette.  
  
 ![Illustrazione di una spline di Bezier.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [Spline di Bézier in GDI+](bezier-splines-in-gdi.md)
- [Procedura: Disegnare una sequenza di spline di Bézier](how-to-draw-a-sequence-of-bezier-splines.md)
