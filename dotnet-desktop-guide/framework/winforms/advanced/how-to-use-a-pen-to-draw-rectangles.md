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
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="bab69-102">Procedura: Usare un oggetto Pen per disegnare rettangoli</span><span class="sxs-lookup"><span data-stu-id="bab69-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="bab69-103">Per creare rettangoli, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bab69-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="bab69-104">L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio il colore e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="bab69-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab69-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bab69-105">Example</span></span>  
 <span data-ttu-id="bab69-106">Nell'esempio seguente viene disegnato un rettangolo con l'angolo superiore sinistro in corrispondenza di (10, 10).</span><span class="sxs-lookup"><span data-stu-id="bab69-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="bab69-107">Il rettangolo ha una larghezza di 100 e un'altezza di 50.</span><span class="sxs-lookup"><span data-stu-id="bab69-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="bab69-108">Il secondo argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore indica che la larghezza della penna è 5 pixel.</span><span class="sxs-lookup"><span data-stu-id="bab69-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="bab69-109">Quando il rettangolo viene disegnato, la penna viene centrata sul limite del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bab69-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="bab69-110">Poiché la larghezza della penna è 5, i lati del rettangolo vengono disegnati a 5 pixel di larghezza, in modo che 1 pixel venga disegnato sul limite, 2 pixel siano disegnati all'interno e 2 pixel vengono disegnati all'esterno.</span><span class="sxs-lookup"><span data-stu-id="bab69-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="bab69-111">Per altri dettagli sull'allineamento della penna, vedere [procedura: impostare la larghezza e l'allineamento della penna](how-to-set-pen-width-and-alignment.md).</span><span class="sxs-lookup"><span data-stu-id="bab69-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="bab69-112">Nella figura seguente viene illustrato il rettangolo risultante.</span><span class="sxs-lookup"><span data-stu-id="bab69-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="bab69-113">Le linee tratteggiate indicano dove sarebbe stato disegnato il rettangolo se la lunghezza della penna era un pixel.</span><span class="sxs-lookup"><span data-stu-id="bab69-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="bab69-114">La visualizzazione ingrandita dell'angolo superiore sinistro del rettangolo indica che le linee nere spesse sono centrate su tali linee tratteggiate.</span><span class="sxs-lookup"><span data-stu-id="bab69-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![Screenshot che mostra il rettangolo disegnato con linee nere e punteggiate.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bab69-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bab69-116">Compiling the Code</span></span>  
 <span data-ttu-id="bab69-117">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bab69-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab69-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bab69-118">See also</span></span>

- [<span data-ttu-id="bab69-119">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="bab69-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
