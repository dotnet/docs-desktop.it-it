---
title: Penne, linee e rettangoli in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963112"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Penne, linee e rettangoli in GDI+
Per creare linee con GDI+ è necessario creare un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce i metodi che eseguono effettivamente il disegno e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio il colore, la larghezza e lo stile della linea.  
  
## <a name="drawing-a-line"></a>Disegno di una linea  
 Per creare una linea, chiamare il <xref:System.Drawing.Graphics.DrawLine%2A> metodo dell' <xref:System.Drawing.Graphics> oggetto. L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawLine%2A> metodo. Nell'esempio seguente viene disegnata una riga dal punto (4, 2) al punto (12, 6):  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi. È ad esempio possibile costruire due <xref:System.Drawing.Point> oggetti e passare gli <xref:System.Drawing.Point> oggetti come argomenti al <xref:System.Drawing.Graphics.DrawLine%2A> Metodo:  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Creazione di una penna  
 È possibile specificare determinati attributi quando si costruisce un <xref:System.Drawing.Pen> oggetto. Un costruttore, ad esempio, `Pen` consente di specificare il colore e la larghezza. Nell'esempio seguente viene disegnata una linea blu di larghezza 2 da (0,0) a (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Linee tratteggiate e estremità di linea  
 L' <xref:System.Drawing.Pen> oggetto espone anche proprietà, ad esempio <xref:System.Drawing.Pen.DashStyle%2A> , che è possibile usare per specificare le funzionalità della riga. Nell'esempio seguente viene disegnata una linea tratteggiata da (100, 50) a (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 È possibile utilizzare le proprietà dell' <xref:System.Drawing.Pen> oggetto per impostare molti più attributi della riga. Le <xref:System.Drawing.Pen.StartCap%2A> <xref:System.Drawing.Pen.EndCap%2A> proprietà e specificano l'aspetto delle estremità della linea; le estremità possono essere flat, Square, arrotondate, triangolari o una forma personalizzata. La <xref:System.Drawing.Pen.LineJoin%2A> proprietà consente di specificare se le linee connesse sono sgolato (unite a angoli acuti), smussate, arrotondate o ritagliate. Nella figura seguente sono illustrate le righe con diversi stili di terminazione e di join.  
  
 ![Linee](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Disegno di un rettangolo  
 Il disegno di rettangoli con GDI+ è simile a quello delle linee di disegno. Per creare un rettangolo, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce un <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio la lunghezza della linea e il colore. L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo. Nell'esempio seguente viene disegnato un rettangolo con il relativo angolo superiore sinistro in (100, 50), una larghezza di 80 e un'altezza pari a 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> è un metodo di overload della <xref:System.Drawing.Graphics> classe, quindi è possibile fornire gli argomenti in diversi modi. È ad esempio possibile costruire un <xref:System.Drawing.Rectangle> oggetto e passare l' <xref:System.Drawing.Rectangle> oggetto al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo come argomento:  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Un <xref:System.Drawing.Rectangle> oggetto dispone di metodi e proprietà per la modifica e la raccolta di informazioni sul rettangolo. Ad esempio, i <xref:System.Drawing.Rectangle.Inflate%2A> <xref:System.Drawing.Rectangle.Offset%2A> metodi e modificano le dimensioni e la posizione del rettangolo. Il <xref:System.Drawing.Rectangle.IntersectsWith%2A> metodo indica se il rettangolo interseca un altro rettangolo specificato e il <xref:System.Drawing.Rectangle.Contains%2A> metodo indica se un punto specificato si trova all'interno del rettangolo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [Procedura: Creare un oggetto Pen](how-to-create-a-pen.md)
- [Procedura: Disegnare una linea in un Windows Form](how-to-draw-a-line-on-a-windows-form.md)
- [Procedura: Disegnare una forma con contorno](how-to-draw-an-outlined-shape.md)
