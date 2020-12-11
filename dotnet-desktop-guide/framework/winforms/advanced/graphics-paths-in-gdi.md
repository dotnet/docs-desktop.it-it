---
title: Percorsi di oggetti Graphics in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951511"
---
# <a name="graphics-paths-in-gdi"></a>Percorsi di oggetti Graphics in GDI+
I percorsi vengono formati combinando linee, rettangoli e curve semplici. Dal Panoramica della [grafica vettoriale](vector-graphics-overview.md) , i blocchi predefiniti di base seguenti si sono dimostrati più utili per il disegno di immagini:  
  
- Linee  
  
- Rettangoli  
  
- Ellissi  
  
- Archi  
  
- Poligoni  
  
- Spline cardinali  
  
- Spline di Bézier  
  
 In GDI+ l' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto consente di raccogliere una sequenza di questi blocchi predefiniti in un'unica unità. L'intera sequenza di linee, rettangoli, poligoni e curve può quindi essere disegnata con una chiamata al <xref:System.Drawing.Graphics.DrawPath%2A> metodo della <xref:System.Drawing.Graphics> classe. Nella figura seguente viene illustrato un percorso creato combinando una linea, un arco, una spline di Bézier e una spline di cardinalità.  
  
 ![Percorso](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>Uso di un percorso  
 La <xref:System.Drawing.Drawing2D.GraphicsPath> classe fornisce i metodi seguenti per la creazione di una sequenza di elementi da disegnare: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> ,, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (per le spline cardinalhe) e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> . Ognuno di questi metodi è sovraccarico; ovvero, ogni metodo supporta diversi elenchi di parametri diversi. Ad esempio, una variante del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve quattro numeri interi e un'altra variante del <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> metodo riceve due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per aggiungere linee, rettangoli e spline di Bézier a un percorso hanno metodi complementari plurali che aggiungono più elementi al percorso in una singola chiamata: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> , <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> . Inoltre, i <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> metodi e hanno metodi complementari, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> , che aggiungono una curva o una torta chiusa al percorso.  
  
 Per tracciare un percorso, sono necessari un <xref:System.Drawing.Graphics> oggetto, un oggetto <xref:System.Drawing.Pen> e un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawPath%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la larghezza e il colore, della riga utilizzata per il rendering del percorso. L' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia la sequenza di linee e curve che costituiscono il percorso. L' <xref:System.Drawing.Pen> oggetto e l' <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto vengono passati come argomenti al <xref:System.Drawing.Graphics.DrawPath%2A> metodo. Nell'esempio seguente viene disegnato un percorso costituito da una linea, un'ellisse e una spline di Bézier:  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 Nella figura seguente viene illustrato il percorso.  
  
 ![Percorso](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 Oltre ad aggiungere linee, rettangoli e curve a un tracciato, è possibile aggiungere percorsi a un percorso. In questo modo è possibile combinare i percorsi esistenti per formare percorsi complessi e di grandi dimensioni.  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 Esistono altri due elementi che è possibile aggiungere a un percorso: stringhe e torte. Una torta è una parte dell'area interna di un'ellisse. Nell'esempio seguente viene creato un percorso da un arco, una spline Cardinal, una stringa e una torta:  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 Nella figura seguente viene illustrato il percorso. Si noti che non è necessario che un percorso sia connesso; l'arco, la spline di cardinalità, la stringa e la torta sono separate.  
  
 ![Percorsi](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
