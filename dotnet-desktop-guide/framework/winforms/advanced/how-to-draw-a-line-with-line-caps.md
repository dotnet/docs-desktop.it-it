---
title: 'Procedura: Disegnare una linea con estremità'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: 34abfc86e980a24ebb835cfd88d2522f8372c68d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962725"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Procedura: Disegnare una linea con estremità
È possibile creare l'inizio o la fine di una riga in una delle diverse forme denominate Caps di riga. GDI+ supporta diversi limiti di riga, ad esempio round, Square, Diamond e Arrowhead.  
  
## <a name="example"></a>Esempio  
 È possibile specificare i limiti di riga per l'inizio di una riga (Cap iniziale), la fine di una riga (estremità finale) o i trattini di una linea tratteggiata (limite del trattino).  
  
 Nell'esempio seguente viene disegnata una linea con una freccia a un'estremità e un arrotondamento all'altra estremità. L'illustrazione mostra la riga risultante:  
  
 ![Illustrazione che mostra una linea con un perno arrotondato.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> . Incollare il codice di esempio nel <xref:System.Windows.Forms.Control.Paint> gestore eventi passando `e` come <xref:System.Windows.Forms.PaintEventArgs> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
