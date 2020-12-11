---
title: 'Procedura: Allineare il testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 3a569284a1c4b43fa7264e0354934436f95b8dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951503"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="14256-102">Procedura: Allineare il testo disegnato</span><span class="sxs-lookup"><span data-stu-id="14256-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="14256-103">Quando si esegue un disegno personalizzato, è spesso consigliabile centrare il testo disegnato su un form o un controllo.</span><span class="sxs-lookup"><span data-stu-id="14256-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="14256-104">È possibile allineare facilmente il testo disegnato con <xref:System.Drawing.Graphics.DrawString%2A> i <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi o creando l'oggetto di formattazione corretto e impostando i flag di formato appropriati.</span><span class="sxs-lookup"><span data-stu-id="14256-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="14256-105">Per creare il testo centrato con GDI+ (DrawString)</span><span class="sxs-lookup"><span data-stu-id="14256-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1. <span data-ttu-id="14256-106">Usare un <xref:System.Drawing.StringFormat> con il <xref:System.Drawing.Graphics.DrawString%2A> metodo appropriato per specificare il testo centrato.</span><span class="sxs-lookup"><span data-stu-id="14256-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="14256-107">Per creare il testo centrato con GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="14256-107">To draw centered text with GDI (DrawText)</span></span>  
  
1. <span data-ttu-id="14256-108">Usare l' <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping e il testo centrato verticalmente e orizzontalmente con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo appropriato.</span><span class="sxs-lookup"><span data-stu-id="14256-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14256-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="14256-109">Compiling the Code</span></span>  
 <span data-ttu-id="14256-110">Gli esempi di codice precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="14256-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14256-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14256-111">See also</span></span>

- [<span data-ttu-id="14256-112">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="14256-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="14256-113">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="14256-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="14256-114">Procedura: Creare tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="14256-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
