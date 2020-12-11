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
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="e730c-102">Procedura: Disegnare una linea con riempimento a trama</span><span class="sxs-lookup"><span data-stu-id="e730c-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="e730c-103">Anziché disegnare una linea con un colore a tinta unita, è possibile disegnare una linea con una trama.</span><span class="sxs-lookup"><span data-stu-id="e730c-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="e730c-104">Per creare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> oggetto e passare tale <xref:System.Drawing.TextureBrush> oggetto a un <xref:System.Drawing.Pen.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="e730c-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="e730c-105">La bitmap associata al pennello trama viene utilizzata per affiancare il piano (invisibile) e quando la penna disegna una linea o una curva, il tratto della penna rileva determinati pixel della trama affiancata.</span><span class="sxs-lookup"><span data-stu-id="e730c-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e730c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e730c-106">Example</span></span>  
 <span data-ttu-id="e730c-107">Nell'esempio seguente viene creato un <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg` .</span><span class="sxs-lookup"><span data-stu-id="e730c-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="e730c-108">Tale bitmap viene utilizzata per costruire un <xref:System.Drawing.TextureBrush> oggetto e l' <xref:System.Drawing.TextureBrush> oggetto viene utilizzato per costruire un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e730c-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="e730c-109">La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> Disegna la bitmap con l'angolo superiore sinistro in corrispondenza di (0, 0).</span><span class="sxs-lookup"><span data-stu-id="e730c-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="e730c-110">La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza l' <xref:System.Drawing.Pen> oggetto per creare un'ellisse con trama.</span><span class="sxs-lookup"><span data-stu-id="e730c-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="e730c-111">La figura seguente mostra la bitmap e l'ellisse con trama:</span><span class="sxs-lookup"><span data-stu-id="e730c-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![Screenshot che mostra la bitmap e l'ellisse con trama.](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e730c-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e730c-113">Compiling the Code</span></span>  
 <span data-ttu-id="e730c-114">Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="e730c-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e730c-115">Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e730c-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="e730c-116">Sostituire `Texture.jpg` con un'immagine valida nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e730c-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e730c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e730c-117">See also</span></span>

- [<span data-ttu-id="e730c-118">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="e730c-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="e730c-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e730c-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
