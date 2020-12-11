---
title: 'Procedura: Disegnare una linea con riempimento a trama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962749"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Procedura: Disegnare una linea con riempimento a trama
Anziché disegnare una linea con un colore a tinta unita, è possibile disegnare una linea con una trama. Per creare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> oggetto e passare tale <xref:System.Drawing.TextureBrush> oggetto a un <xref:System.Drawing.Pen.%23ctor%2A> costruttore. La bitmap associata al pennello trama viene utilizzata per affiancare il piano (invisibile) e quando la penna disegna una linea o una curva, il tratto della penna rileva determinati pixel della trama affiancata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg` . Tale bitmap viene utilizzata per costruire un <xref:System.Drawing.TextureBrush> oggetto e l' <xref:System.Drawing.TextureBrush> oggetto viene utilizzato per costruire un <xref:System.Drawing.Pen> oggetto. La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> Disegna la bitmap con l'angolo superiore sinistro in corrispondenza di (0, 0). La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza l' <xref:System.Drawing.Pen> oggetto per creare un'ellisse con trama.  
  
 La figura seguente mostra la bitmap e l'ellisse con trama:  
  
 ![Screenshot che mostra la bitmap e l'ellisse con trama.](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> . Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire `Texture.jpg` con un'immagine valida nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
