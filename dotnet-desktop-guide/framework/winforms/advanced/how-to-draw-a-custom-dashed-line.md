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
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="a89c8-102">Procedura: Disegnare una linea tratteggiata personalizzata</span><span class="sxs-lookup"><span data-stu-id="a89c8-102">How to: Draw a Custom Dashed Line</span></span>
<span data-ttu-id="a89c8-103">GDI+ fornisce diversi stili Dash elencati nell' <xref:System.Drawing.Drawing2D.DashStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a89c8-103">GDI+ provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="a89c8-104">Se gli stili Dash standard non soddisfano le proprie esigenze, è possibile creare un modello Dash personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a89c8-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89c8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a89c8-105">Example</span></span>  
 <span data-ttu-id="a89c8-106">Per creare una linea tratteggiata personalizzata, inserire le lunghezze dei trattini e degli spazi in una matrice e assegnare la matrice come valore della <xref:System.Drawing.Pen.DashPattern%2A> proprietà di un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a89c8-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="a89c8-107">Nell'esempio seguente viene disegnata una linea tratteggiata personalizzata basata sulla matrice `{5, 2, 15, 4}` .</span><span class="sxs-lookup"><span data-stu-id="a89c8-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="a89c8-108">Se si moltiplicano gli elementi della matrice in base alla larghezza della penna di 5, si ottiene `{25, 10, 75, 20}` .</span><span class="sxs-lookup"><span data-stu-id="a89c8-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="a89c8-109">I trattini visualizzati si alternano con una lunghezza compresa tra 25 e 75 e gli spazi si alternano con una lunghezza compresa tra 10 e 20.</span><span class="sxs-lookup"><span data-stu-id="a89c8-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="a89c8-110">Nella figura seguente viene illustrata la linea tratteggiata risultante.</span><span class="sxs-lookup"><span data-stu-id="a89c8-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="a89c8-111">Si noti che il trattino finale deve essere più breve di 25 unità in modo che la riga possa terminare in corrispondenza di (405, 5).</span><span class="sxs-lookup"><span data-stu-id="a89c8-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="a89c8-112">![Illustrazione che mostra una linea tratteggiata.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="a89c8-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a89c8-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a89c8-113">Compiling the Code</span></span>  
 <span data-ttu-id="a89c8-114">Creare un Windows Form e gestire l'evento del modulo <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="a89c8-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="a89c8-115">Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a89c8-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89c8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a89c8-116">See also</span></span>

- [<span data-ttu-id="a89c8-117">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="a89c8-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
