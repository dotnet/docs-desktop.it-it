---
title: 'Procedura: Unire le linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963367"
---
# <a name="how-to-join-lines"></a>Procedura: Unire le linee
Un join a linee è l'area comune costituita da due righe le cui estremità soddisfano o si sovrappongono. In GDI+ sono disponibili tre stili di join a linee: Miter, smussatura e round. Lo stile di join a linee è una proprietà della <xref:System.Drawing.Pen> classe. Quando si specifica uno stile di join di riga per un <xref:System.Drawing.Pen> oggetto, lo stile di join verrà applicato a tutte le linee connesse in qualsiasi <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto disegnato usando tale penna.  
  
 Nella figura seguente sono illustrati i risultati dell'esempio di join a linee smussate.  
  
 ![Illustrazione che mostra le linee Unite.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a>Esempio  
 È possibile specificare lo stile di aggiunta a linee usando la <xref:System.Drawing.Pen.LineJoin%2A> proprietà della <xref:System.Drawing.Pen> classe. Nell'esempio viene illustrato un join a linee smussate tra una linea orizzontale e una linea verticale. Nel codice seguente il valore <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assegnato alla <xref:System.Drawing.Pen.LineJoin%2A> proprietà è un membro dell' <xref:System.Drawing.Drawing2D.LineJoin> enumerazione. Gli altri membri dell' <xref:System.Drawing.Drawing2D.LineJoin> enumerazione sono <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round> .  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
