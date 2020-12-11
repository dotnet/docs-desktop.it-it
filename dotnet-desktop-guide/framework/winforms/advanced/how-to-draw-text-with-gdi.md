---
title: 'Procedura: Disegnare testo con GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962659"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="5b73d-102">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="5b73d-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="5b73d-103">Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo nella <xref:System.Windows.Forms.TextRenderer> classe, è possibile accedere alla funzionalità GDI per il disegno di testo in un form o un controllo.</span><span class="sxs-lookup"><span data-stu-id="5b73d-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="5b73d-104">Il rendering del testo GDI offre in genere prestazioni migliori e una misurazione più accurata del testo rispetto a GDI+.</span><span class="sxs-lookup"><span data-stu-id="5b73d-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b73d-105">I <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi della <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa.</span><span class="sxs-lookup"><span data-stu-id="5b73d-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="5b73d-106">Quando si esegue la stampa, utilizzare sempre i <xref:System.Drawing.Graphics.DrawString%2A> metodi della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="5b73d-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b73d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b73d-107">Example</span></span>  
 <span data-ttu-id="5b73d-108">Nell'esempio di codice riportato di seguito viene illustrato come creare testo su più righe all'interno di un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="5b73d-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="5b73d-109">Per eseguire il rendering del testo con la <xref:System.Windows.Forms.TextRenderer> classe, è necessario un oggetto <xref:System.Drawing.IDeviceContext> , ad esempio un oggetto <xref:System.Drawing.Graphics> e un oggetto <xref:System.Drawing.Font> , un percorso per disegnare il testo e il colore in cui deve essere disegnato.</span><span class="sxs-lookup"><span data-stu-id="5b73d-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="5b73d-110">Facoltativamente, è possibile specificare la formattazione del testo utilizzando l' <xref:System.Windows.Forms.TextFormatFlags> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5b73d-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="5b73d-111">Per ulteriori informazioni su come ottenere un oggetto <xref:System.Drawing.Graphics> , vedere [procedura: creare oggetti grafici per il disegno](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="5b73d-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="5b73d-112">Per altre informazioni sulla costruzione di un oggetto <xref:System.Drawing.Font> , vedere [procedura: costruire famiglie di caratteri e tipi](how-to-construct-font-families-and-fonts.md)di carattere.</span><span class="sxs-lookup"><span data-stu-id="5b73d-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b73d-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5b73d-113">Compiling the Code</span></span>  
 <span data-ttu-id="5b73d-114">L'esempio di codice precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="5b73d-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b73d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b73d-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="5b73d-116">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="5b73d-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
