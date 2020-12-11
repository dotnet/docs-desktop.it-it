---
title: 'Procedura: Usare un oggetto Pen per disegnare rettangoli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962449"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Procedura: Usare un oggetto Pen per disegnare rettangoli
Per creare rettangoli, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio il colore e la larghezza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnato un rettangolo con l'angolo superiore sinistro in corrispondenza di (10, 10). Il rettangolo ha una larghezza di 100 e un'altezza di 50. Il secondo argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore indica che la larghezza della penna è 5 pixel.  
  
 Quando il rettangolo viene disegnato, la penna viene centrata sul limite del rettangolo. Poiché la larghezza della penna è 5, i lati del rettangolo vengono disegnati a 5 pixel di larghezza, in modo che 1 pixel venga disegnato sul limite, 2 pixel siano disegnati all'interno e 2 pixel vengono disegnati all'esterno. Per altri dettagli sull'allineamento della penna, vedere [procedura: impostare la larghezza e l'allineamento della penna](how-to-set-pen-width-and-alignment.md).  
  
 Nella figura seguente viene illustrato il rettangolo risultante. Le linee tratteggiate indicano dove sarebbe stato disegnato il rettangolo se la lunghezza della penna era un pixel. La visualizzazione ingrandita dell'angolo superiore sinistro del rettangolo indica che le linee nere spesse sono centrate su tali linee tratteggiate.  
  
 ![Screenshot che mostra il rettangolo disegnato con linee nere e punteggiate.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
