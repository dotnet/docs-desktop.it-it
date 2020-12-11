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
# <a name="how-to-join-lines"></a><span data-ttu-id="7a365-102">Procedura: Unire le linee</span><span class="sxs-lookup"><span data-stu-id="7a365-102">How to: Join Lines</span></span>
<span data-ttu-id="7a365-103">Un join a linee è l'area comune costituita da due righe le cui estremità soddisfano o si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="7a365-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> <span data-ttu-id="7a365-104">In GDI+ sono disponibili tre stili di join a linee: Miter, smussatura e round.</span><span class="sxs-lookup"><span data-stu-id="7a365-104">GDI+ provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="7a365-105">Lo stile di join a linee è una proprietà della <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="7a365-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="7a365-106">Quando si specifica uno stile di join di riga per un <xref:System.Drawing.Pen> oggetto, lo stile di join verrà applicato a tutte le linee connesse in qualsiasi <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto disegnato usando tale penna.</span><span class="sxs-lookup"><span data-stu-id="7a365-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="7a365-107">Nella figura seguente sono illustrati i risultati dell'esempio di join a linee smussate.</span><span class="sxs-lookup"><span data-stu-id="7a365-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![Illustrazione che mostra le linee Unite.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="7a365-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a365-109">Example</span></span>  
 <span data-ttu-id="7a365-110">È possibile specificare lo stile di aggiunta a linee usando la <xref:System.Drawing.Pen.LineJoin%2A> proprietà della <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="7a365-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="7a365-111">Nell'esempio viene illustrato un join a linee smussate tra una linea orizzontale e una linea verticale.</span><span class="sxs-lookup"><span data-stu-id="7a365-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="7a365-112">Nel codice seguente il valore <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assegnato alla <xref:System.Drawing.Pen.LineJoin%2A> proprietà è un membro dell' <xref:System.Drawing.Drawing2D.LineJoin> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7a365-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="7a365-113">Gli altri membri dell' <xref:System.Drawing.Drawing2D.LineJoin> enumerazione sono <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round> .</span><span class="sxs-lookup"><span data-stu-id="7a365-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a365-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7a365-114">Compiling the Code</span></span>  
 <span data-ttu-id="7a365-115">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="7a365-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a365-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a365-116">See also</span></span>

- [<span data-ttu-id="7a365-117">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="7a365-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
