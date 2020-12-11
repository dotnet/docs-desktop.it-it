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
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="db1c1-102">Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="db1c1-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="db1c1-103">Quando si crea un oggetto <xref:System.Drawing.Pen> , è possibile specificare la larghezza della penna come uno degli argomenti per il costruttore.</span><span class="sxs-lookup"><span data-stu-id="db1c1-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="db1c1-104">È anche possibile modificare la larghezza della penna con la <xref:System.Drawing.Pen.Width%2A> proprietà della <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="db1c1-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="db1c1-105">Una linea teorica ha una larghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="db1c1-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="db1c1-106">Quando si crea una linea con una larghezza di 1 pixel, i pixel vengono centrati sulla linea teorica.</span><span class="sxs-lookup"><span data-stu-id="db1c1-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="db1c1-107">Se si estrae una linea più ampia di un pixel, i pixel vengono centrati sulla linea teorica o appaiono su un lato della linea teorica.</span><span class="sxs-lookup"><span data-stu-id="db1c1-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="db1c1-108">È possibile impostare la proprietà allineamento penna di un oggetto <xref:System.Drawing.Pen> per determinare il modo in cui i pixel disegnati con tale penna verranno posizionati in relazione alle linee teoriche.</span><span class="sxs-lookup"><span data-stu-id="db1c1-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="db1c1-109">I valori <xref:System.Drawing.Drawing2D.PenAlignment.Center> , <xref:System.Drawing.Drawing2D.PenAlignment.Outset> e <xref:System.Drawing.Drawing2D.PenAlignment.Inset> visualizzati negli esempi di codice seguenti sono membri dell' <xref:System.Drawing.Drawing2D.PenAlignment> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="db1c1-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="db1c1-110">Nell'esempio di codice seguente viene disegnata una riga due volte: una volta con una penna nera di larghezza 1 e una volta con una penna verde di larghezza 10.</span><span class="sxs-lookup"><span data-stu-id="db1c1-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="db1c1-111">Per variare la larghezza di una penna</span><span class="sxs-lookup"><span data-stu-id="db1c1-111">To vary the width of a pen</span></span>  
  
- <span data-ttu-id="db1c1-112">Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà su <xref:System.Drawing.Drawing2D.PenAlignment.Center> (impostazione predefinita) per specificare che i pixel disegnati con la penna verde saranno centrati sulla linea teorica.</span><span class="sxs-lookup"><span data-stu-id="db1c1-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="db1c1-113">Nella figura seguente viene illustrata la riga risultante.</span><span class="sxs-lookup"><span data-stu-id="db1c1-113">The following illustration shows the resulting line.</span></span>  
  
     ![Una linea sottile nera con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     <span data-ttu-id="db1c1-115">L'esempio di codice seguente disegna un rettangolo due volte: una volta con una penna nera di larghezza 1 e una volta con una penna verde di larghezza 10.</span><span class="sxs-lookup"><span data-stu-id="db1c1-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="db1c1-116">Per modificare l'allineamento di una penna</span><span class="sxs-lookup"><span data-stu-id="db1c1-116">To change the alignment of a pen</span></span>  
  
- <span data-ttu-id="db1c1-117">Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà su <xref:System.Drawing.Drawing2D.PenAlignment.Center> per specificare che i pixel disegnati con la penna verde saranno centrati sul limite del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="db1c1-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="db1c1-118">Nella figura seguente viene illustrato il rettangolo risultante:</span><span class="sxs-lookup"><span data-stu-id="db1c1-118">The following illustration shows the resulting rectangle:</span></span>
  
     ![Rettangolo disegnato con linee sottili nere con evidenziazione verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="db1c1-120">Per creare una penna di inserimento</span><span class="sxs-lookup"><span data-stu-id="db1c1-120">To create an inset pen</span></span>  
  
- <span data-ttu-id="db1c1-121">Modificare l'allineamento della penna verde modificando la terza istruzione nell'esempio di codice precedente come segue:</span><span class="sxs-lookup"><span data-stu-id="db1c1-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="db1c1-122">Ora i pixel nella linea verde ampia vengono visualizzati all'interno del rettangolo, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="db1c1-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration:</span></span>
  
     ![Rettangolo disegnato con linee nere con la linea verde ampia all'interno.](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a><span data-ttu-id="db1c1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db1c1-124">See also</span></span>

- [<span data-ttu-id="db1c1-125">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="db1c1-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="db1c1-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="db1c1-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
