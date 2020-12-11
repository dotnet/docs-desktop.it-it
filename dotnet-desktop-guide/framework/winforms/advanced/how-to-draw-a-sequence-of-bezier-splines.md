---
title: 'Procedura: creare una sequenza di B&#233;spline Zier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962713"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>Procedura: creare una sequenza di B&#233;spline Zier
È possibile usare il <xref:System.Drawing.Graphics.DrawBeziers%2A> metodo della <xref:System.Drawing.Graphics> classe per creare una sequenza di spline di Bézier connesse.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnata una curva costituita da due spline di Bézier connesse. L'endpoint della prima spline di Bézier è il punto iniziale della seconda spline di Bézier.  
  
 La figura seguente mostra le spline connesse insieme ai sette punti:  
  
 ![Immagine che mostra le spline connesse insieme a sette punti.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Spline di Bézier in GDI+](bezier-splines-in-gdi.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
