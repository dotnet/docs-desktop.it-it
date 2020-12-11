---
title: Ellissi e archi in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960691"
---
# <a name="ellipses-and-arcs-in-gdi"></a>Ellissi e archi in GDI+
È possibile creare facilmente ellissi e archi usando i <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> metodi e della <xref:System.Drawing.Graphics> classe.  
  
## <a name="drawing-an-ellipse"></a>Disegno di un'ellisse  
 Per creare un'ellisse, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering dell'ellisse. L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo. Gli argomenti rimanenti passati al <xref:System.Drawing.Graphics.DrawEllipse%2A> Metodo specificano il rettangolo di delimitazione per l'ellisse. Nell'illustrazione seguente viene mostrata un'ellisse insieme al rettangolo di delimitazione.  
  
 ![Ellissi e archi](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 Nell'esempio seguente viene disegnata un'ellisse. il rettangolo di delimitazione ha una larghezza di 80, un'altezza di 40 e un angolo superiore sinistro di (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi. È ad esempio possibile costruire un oggetto <xref:System.Drawing.Rectangle> e passare al <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo come argomento:  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Disegno di un arco  
 Un arco è una parte di un'ellisse. Per creare un arco, chiamare il <xref:System.Drawing.Graphics.DrawArc%2A> metodo della <xref:System.Drawing.Graphics> classe. I parametri del <xref:System.Drawing.Graphics.DrawArc%2A> metodo sono gli stessi dei parametri del <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo, ad eccezione del fatto che <xref:System.Drawing.Graphics.DrawArc%2A> richiede un angolo iniziale e un angolo di apertura. Nell'esempio seguente viene disegnato un arco con un angolo iniziale di 30 gradi e un angolo di apertura di 180 gradi:  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 Nella figura seguente vengono illustrati l'arco, l'ellisse e il rettangolo di delimitazione.  
  
 ![Ellissi e archi](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
- [Procedura: Disegnare una forma con contorno](how-to-draw-an-outlined-shape.md)
