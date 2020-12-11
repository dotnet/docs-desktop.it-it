---
title: 'Procedura: Usare un oggetto Pen per disegnare linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963223"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Procedura: Usare un oggetto Pen per disegnare linee
Per creare linee, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawLine%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio il colore e la larghezza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnata una riga da (20, 10) a (300, 100). La prima istruzione usa il <xref:System.Drawing.Pen.%23ctor%2A> costruttore della classe per creare una penna nera. L'unico argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore è un <xref:System.Drawing.Color> oggetto creato con il <xref:System.Drawing.Color.FromArgb%2A> metodo. I valori utilizzati per creare l' <xref:System.Drawing.Color> oggetto, (255, 0, 0, 0), corrispondono ai componenti alfa, rosso, verde e blu del colore. Questi valori definiscono una penna nera opaca.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Pen>
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Penne, linee e rettangoli in GDI+](pens-lines-and-rectangles-in-gdi.md)
