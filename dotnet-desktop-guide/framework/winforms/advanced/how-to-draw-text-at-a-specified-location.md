---
title: 'Procedura: Disegnare testo in una posizione specificata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962668"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="5d041-102">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="5d041-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="5d041-103">Quando si esegue un disegno personalizzato, è possibile tracciare il testo in un'unica riga orizzontale a partire da un punto specificato.</span><span class="sxs-lookup"><span data-stu-id="5d041-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="5d041-104">È possibile creare il testo in questo modo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload della <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> <xref:System.Drawing.PointF> parametro o.</span><span class="sxs-lookup"><span data-stu-id="5d041-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="5d041-105">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede anche un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="5d041-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="5d041-106">È anche possibile usare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un oggetto <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="5d041-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="5d041-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> richiede anche un oggetto <xref:System.Drawing.Color> e un oggetto <xref:System.Drawing.Font> .</span><span class="sxs-lookup"><span data-stu-id="5d041-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="5d041-108">La figura seguente mostra l'output del testo disegnato in un punto specificato quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload.</span><span class="sxs-lookup"><span data-stu-id="5d041-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![Screenshot che mostra l'output del testo in corrispondenza di un punto specificato.](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="5d041-110">Per creare una riga di testo con GDI+</span><span class="sxs-lookup"><span data-stu-id="5d041-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="5d041-111">Usare il <xref:System.Drawing.Graphics.DrawString%2A> metodo, passando il testo desiderato, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> , <xref:System.Drawing.Font> e <xref:System.Drawing.Brush> .</span><span class="sxs-lookup"><span data-stu-id="5d041-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="5d041-112">Per creare una riga di testo con GDI</span><span class="sxs-lookup"><span data-stu-id="5d041-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="5d041-113">Usare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo, passando il testo desiderato,, <xref:System.Drawing.Point> <xref:System.Drawing.Font> e <xref:System.Drawing.Color> .</span><span class="sxs-lookup"><span data-stu-id="5d041-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d041-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5d041-114">Compiling the Code</span></span>  
 <span data-ttu-id="5d041-115">Gli esempi precedenti richiedono:</span><span class="sxs-lookup"><span data-stu-id="5d041-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="5d041-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="5d041-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d041-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d041-117">See also</span></span>

- [<span data-ttu-id="5d041-118">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="5d041-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="5d041-119">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="5d041-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="5d041-120">Procedura: Creare tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="5d041-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="5d041-121">Procedura: Disegnare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="5d041-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
