---
title: Curve aperte e chiuse in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963115"
---
# <a name="open-and-closed-curves-in-gdi"></a>Curve aperte e chiuse in GDI+
Nella figura seguente sono illustrate due curve: una aperta e una chiusa.  
  
 ![Apri & curve chiuse](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Interfaccia gestita per curve  
 Le curve chiuse hanno una parte interna e pertanto possono essere riempite con un pennello. La <xref:System.Drawing.Graphics> classe in GDI+ fornisce i metodi seguenti per compilare forme e curve chiuse: <xref:System.Drawing.Graphics.FillRectangle%2A> , <xref:System.Drawing.Graphics.FillEllipse%2A> , <xref:System.Drawing.Graphics.FillPie%2A> , <xref:System.Drawing.Graphics.FillPolygon%2A> , <xref:System.Drawing.Graphics.FillClosedCurve%2A> , <xref:System.Drawing.Graphics.FillPath%2A> e <xref:System.Drawing.Graphics.FillRegion%2A> . Ogni volta che si chiama uno di questi metodi, è necessario passare uno dei tipi di pennello specifici ( <xref:System.Drawing.SolidBrush> ,, <xref:System.Drawing.Drawing2D.HatchBrush> <xref:System.Drawing.TextureBrush> , <xref:System.Drawing.Drawing2D.LinearGradientBrush> o <xref:System.Drawing.Drawing2D.PathGradientBrush> ) come argomento.  
  
 Il <xref:System.Drawing.Graphics.FillPie%2A> metodo è un complemento al <xref:System.Drawing.Graphics.DrawArc%2A> metodo. Così come il <xref:System.Drawing.Graphics.DrawArc%2A> metodo disegna una parte del contorno di un'ellisse, il <xref:System.Drawing.Graphics.FillPie%2A> metodo riempie una parte dell'area interna di un'ellisse. Nell'esempio seguente viene disegnato un arco e viene riempita la parte corrispondente dell'interno dell'ellisse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 Nella figura seguente vengono illustrati l'arco e la torta piena.  
  
 ![Apri & curve chiuse](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 Il <xref:System.Drawing.Graphics.FillClosedCurve%2A> metodo è un complemento al <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo. Entrambi i metodi chiudono automaticamente la curva connettendo il punto finale al punto iniziale. Nell'esempio seguente viene disegnata una curva che passa attraverso (0, 0), (60, 20) e (40, 50). La curva viene quindi chiusa automaticamente connettendosi (40, 50) al punto iniziale (0, 0) e l'interno viene riempito con un colore a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie l'interno delle parti separate di un percorso. Se una parte di un tracciato non costituisce una curva o una forma chiusa, il <xref:System.Drawing.Graphics.FillPath%2A> metodo chiude automaticamente tale parte del percorso prima di compilarlo. Nell'esempio seguente viene disegnato e compilato un percorso costituito da un arco, una spline di cardinalità, una stringa e una torta:  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 Nella figura seguente viene illustrato il percorso con e senza il riempimento a tinta unita. Si noti che il testo nella stringa è delineato, ma non riempito, dal <xref:System.Drawing.Graphics.DrawPath%2A> metodo. Si tratta del <xref:System.Drawing.Graphics.FillPath%2A> metodo che dipinge gli interni dei caratteri nella stringa.  
  
 ![Stringa in un percorso](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
