---
title: 'Procedura: Disegnare una linea tratteggiata personalizzata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951450"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Procedura: Disegnare una linea tratteggiata personalizzata
GDI+ fornisce diversi stili Dash elencati nell' <xref:System.Drawing.Drawing2D.DashStyle> enumerazione. Se gli stili Dash standard non soddisfano le proprie esigenze, è possibile creare un modello Dash personalizzato.  
  
## <a name="example"></a>Esempio  
 Per creare una linea tratteggiata personalizzata, inserire le lunghezze dei trattini e degli spazi in una matrice e assegnare la matrice come valore della <xref:System.Drawing.Pen.DashPattern%2A> proprietà di un <xref:System.Drawing.Pen> oggetto. Nell'esempio seguente viene disegnata una linea tratteggiata personalizzata basata sulla matrice `{5, 2, 15, 4}` . Se si moltiplicano gli elementi della matrice in base alla larghezza della penna di 5, si ottiene `{25, 10, 75, 20}` . I trattini visualizzati si alternano con una lunghezza compresa tra 25 e 75 e gli spazi si alternano con una lunghezza compresa tra 10 e 20.  
  
 Nella figura seguente viene illustrata la linea tratteggiata risultante. Si noti che il trattino finale deve essere più breve di 25 unità in modo che la riga possa terminare in corrispondenza di (405, 5).  
  
 ![Illustrazione che mostra una linea tratteggiata.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> . Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
