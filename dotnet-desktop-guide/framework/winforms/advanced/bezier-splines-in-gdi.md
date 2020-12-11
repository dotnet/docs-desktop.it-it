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
# <a name="b233zier-splines-in-gdi"></a>B&#233;spline Zier in GDI+
Una spline di Bézier è una curva specificata da quattro punti: due punti finali (P1 e P2) e due punti di controllo (C1 e C2). La curva inizia a P1 e termina in corrispondenza di P2. La curva non passa attraverso i punti di controllo, ma i punti di controllo fungono da magneti, spostando la curva in determinate direzioni e influenzando il modo in cui la curva curva. La figura seguente mostra una curva di Bézier insieme ai relativi endpoint e punti di controllo.  
  
 ![Spline di Bezier](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 La curva inizia da P1 e viene spostata verso il punto di controllo C1. La linea tangente alla curva in P1 è la linea disegnata da P1 a C1. La linea tangente nell'endpoint P2 è la linea disegnata da C2 a P2.  
  
## <a name="drawing-bzier-splines"></a>Disegno di spline Bézier  
 Per creare una spline di Bézier, è necessario disporre di un'istanza della <xref:System.Drawing.Graphics> classe e di un oggetto <xref:System.Drawing.Pen> . L'istanza della <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawBezier%2A> metodo e <xref:System.Drawing.Pen> archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering della curva. <xref:System.Drawing.Pen>Viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawBezier%2A> metodo. Gli argomenti rimanenti passati al <xref:System.Drawing.Graphics.DrawBezier%2A> metodo sono gli endpoint e i punti di controllo. Nell'esempio seguente viene disegnata una spline Bézier con punto iniziale (0,0), punti di controllo (40, 20) e (80, 150) e punto finale (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Nella figura seguente vengono illustrati la curva, i punti di controllo e due linee tangente.  
  
 ![Spline di Bezier](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Le spline di Bézier sono state originariamente sviluppate da Pierre Bézier per la progettazione nel settore automobilistico. Poiché sono risultate utili in molti tipi di progettazione assistita da computer e vengono usati anche per definire le strutture dei tipi di carattere. Le spline di Bézier possono produrre un'ampia gamma di forme, alcune delle quali sono illustrate nella figura seguente.  
  
 ![Percorsi](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
