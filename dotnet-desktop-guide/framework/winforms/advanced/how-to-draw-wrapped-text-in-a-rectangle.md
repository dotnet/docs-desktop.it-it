---
title: 'Procedura: Disegnare testo disposto su più righe in un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962632"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="77cd6-102">Procedura: Disegnare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="77cd6-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="77cd6-103">È possibile creare testo incapsulato in un rettangolo usando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload della <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Rectangle> parametro o <xref:System.Drawing.RectangleF> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="77cd6-104">Si utilizzeranno anche un oggetto <xref:System.Drawing.Brush> e un oggetto <xref:System.Drawing.Font> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="77cd6-105">È anche possibile creare testo incapsulato in un rettangolo usando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un oggetto <xref:System.Drawing.Rectangle> e un <xref:System.Windows.Forms.TextFormatFlags> parametro.</span><span class="sxs-lookup"><span data-stu-id="77cd6-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="77cd6-106">Si utilizzeranno anche un oggetto <xref:System.Drawing.Color> e un oggetto <xref:System.Drawing.Font> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="77cd6-107">Nell'illustrazione seguente viene mostrato l'output del testo disegnato nel rettangolo quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> Metodo:</span><span class="sxs-lookup"><span data-stu-id="77cd6-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![Screenshot che mostra l'output quando si usa il metodo DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="77cd6-109">Per creare testo incapsulato in un rettangolo con GDI+</span><span class="sxs-lookup"><span data-stu-id="77cd6-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="77cd6-110">Usare il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload, passando il testo desiderato, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> , <xref:System.Drawing.Font> e <xref:System.Drawing.Brush> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="77cd6-111">Per creare testo incapsulato in un rettangolo con GDI</span><span class="sxs-lookup"><span data-stu-id="77cd6-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="77cd6-112">Usare il <xref:System.Windows.Forms.TextFormatFlags> valore di enumerazione per specificare che il testo deve essere incluso nel <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload, passando il testo desiderato, <xref:System.Drawing.Rectangle> <xref:System.Drawing.Font> e <xref:System.Drawing.Color> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="77cd6-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="77cd6-113">Compiling the Code</span></span>  
 <span data-ttu-id="77cd6-114">Gli esempi precedenti richiedono:</span><span class="sxs-lookup"><span data-stu-id="77cd6-114">The previous examples require:</span></span>  
  
- <span data-ttu-id="77cd6-115"><xref:System.Windows.Forms.PaintEventArgs>`e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="77cd6-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77cd6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77cd6-116">See also</span></span>

- [<span data-ttu-id="77cd6-117">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="77cd6-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="77cd6-118">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="77cd6-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="77cd6-119">Procedura: Creare tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="77cd6-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="77cd6-120">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="77cd6-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
