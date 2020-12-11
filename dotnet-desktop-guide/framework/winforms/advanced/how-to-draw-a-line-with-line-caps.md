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
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="c05e9-102">Procedura: Disegnare una linea con estremità</span><span class="sxs-lookup"><span data-stu-id="c05e9-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="c05e9-103">È possibile creare l'inizio o la fine di una riga in una delle diverse forme denominate Caps di riga.</span><span class="sxs-lookup"><span data-stu-id="c05e9-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> <span data-ttu-id="c05e9-104">GDI+ supporta diversi limiti di riga, ad esempio round, Square, Diamond e Arrowhead.</span><span class="sxs-lookup"><span data-stu-id="c05e9-104">GDI+ supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c05e9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c05e9-105">Example</span></span>  
 <span data-ttu-id="c05e9-106">È possibile specificare i limiti di riga per l'inizio di una riga (Cap iniziale), la fine di una riga (estremità finale) o i trattini di una linea tratteggiata (limite del trattino).</span><span class="sxs-lookup"><span data-stu-id="c05e9-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="c05e9-107">Nell'esempio seguente viene disegnata una linea con una freccia a un'estremità e un arrotondamento all'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="c05e9-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="c05e9-108">L'illustrazione mostra la riga risultante:</span><span class="sxs-lookup"><span data-stu-id="c05e9-108">The illustration shows the resulting line:</span></span>  
  
 ![Illustrazione che mostra una linea con un perno arrotondato.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c05e9-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c05e9-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="c05e9-111">Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="c05e9-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c05e9-112">Incollare il codice di esempio nel <xref:System.Windows.Forms.Control.Paint> gestore eventi passando `e` come <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="c05e9-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05e9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c05e9-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="c05e9-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c05e9-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c05e9-115">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="c05e9-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
