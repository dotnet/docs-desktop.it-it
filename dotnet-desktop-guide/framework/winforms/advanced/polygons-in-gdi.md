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
# <a name="polygons-in-gdi"></a>Poligoni in GDI+
Un poligono è una forma chiusa con tre o più lati dritti. Ad esempio, un triangolo è un poligono con tre lati, un rettangolo è un poligono con quattro lati e un pentagono è un poligono con cinque lati. Nella figura seguente vengono illustrati diversi poligoni.  
  
 ![Poligoni](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Disegno di un poligono  
 Per creare un poligono, sono necessari un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Pen> oggetto e una matrice di <xref:System.Drawing.Point> oggetti (o <xref:System.Drawing.PointF> ). L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo. L' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per eseguire il rendering del poligono e la matrice di <xref:System.Drawing.Point> oggetti archivia i punti da connettere tramite linee rette. L' <xref:System.Drawing.Pen> oggetto e la matrice di <xref:System.Drawing.Point> oggetti vengono passati come argomenti al <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo. Nell'esempio seguente viene disegnato un poligono a tre facce. Si noti che sono presenti solo tre punti in `myPointArray` : (0, 0), (50, 30) e (30, 60). Il <xref:System.Drawing.Graphics.DrawPolygon%2A> metodo chiude automaticamente il poligono disegnando una riga da (30, 60) al punto iniziale (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Nella figura seguente viene illustrato il poligono.  
  
 ![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
