---
title: "Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963283"
---
# <a name="how-to-set-pen-width-and-alignment"></a>Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen
Quando si crea un oggetto <xref:System.Drawing.Pen> , è possibile specificare la larghezza della penna come uno degli argomenti per il costruttore. È anche possibile modificare la larghezza della penna con la <xref:System.Drawing.Pen.Width%2A> proprietà della <xref:System.Drawing.Pen> classe.  
  
 Una linea teorica ha una larghezza pari a 0. Quando si crea una linea con una larghezza di 1 pixel, i pixel vengono centrati sulla linea teorica. Se si estrae una linea più ampia di un pixel, i pixel vengono centrati sulla linea teorica o appaiono su un lato della linea teorica. È possibile impostare la proprietà allineamento penna di un oggetto <xref:System.Drawing.Pen> per determinare il modo in cui i pixel disegnati con tale penna verranno posizionati in relazione alle linee teoriche.  
  
 I valori <xref:System.Drawing.Drawing2D.PenAlignment.Center> , <xref:System.Drawing.Drawing2D.PenAlignment.Outset> e <xref:System.Drawing.Drawing2D.PenAlignment.Inset> visualizzati negli esempi di codice seguenti sono membri dell' <xref:System.Drawing.Drawing2D.PenAlignment> enumerazione.  
  
 Nell'esempio di codice seguente viene disegnata una riga due volte: una volta con una penna nera di larghezza 1 e una volta con una penna verde di larghezza 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Per variare la larghezza di una penna  
  
- Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà su <xref:System.Drawing.Drawing2D.PenAlignment.Center> (impostazione predefinita) per specificare che i pixel disegnati con la penna verde saranno centrati sulla linea teorica. Nella figura seguente viene illustrata la riga risultante.  
  
     ![Una linea sottile nera con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     L'esempio di codice seguente disegna un rettangolo due volte: una volta con una penna nera di larghezza 1 e una volta con una penna verde di larghezza 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>Per modificare l'allineamento di una penna  
  
- Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà su <xref:System.Drawing.Drawing2D.PenAlignment.Center> per specificare che i pixel disegnati con la penna verde saranno centrati sul limite del rettangolo.  
  
     Nella figura seguente viene illustrato il rettangolo risultante:
  
     ![Rettangolo disegnato con linee sottili nere con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>Per creare una penna di inserimento  
  
- Modificare l'allineamento della penna verde modificando la terza istruzione nell'esempio di codice precedente come segue:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Ora i pixel nella linea verde ampia vengono visualizzati all'interno del rettangolo, come illustrato nella figura seguente:
  
     ![Rettangolo disegnato con linee nere con la linea verde ampia all'interno.](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a>Vedere anche

- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
