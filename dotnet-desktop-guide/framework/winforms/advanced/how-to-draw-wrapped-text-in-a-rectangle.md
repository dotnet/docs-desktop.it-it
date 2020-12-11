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
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Procedura: Disegnare testo disposto su più righe in un rettangolo
È possibile creare testo incapsulato in un rettangolo usando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload della <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Rectangle> parametro o <xref:System.Drawing.RectangleF> . Si utilizzeranno anche un oggetto <xref:System.Drawing.Brush> e un oggetto <xref:System.Drawing.Font> .  
  
 È anche possibile creare testo incapsulato in un rettangolo usando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un oggetto <xref:System.Drawing.Rectangle> e un <xref:System.Windows.Forms.TextFormatFlags> parametro. Si utilizzeranno anche un oggetto <xref:System.Drawing.Color> e un oggetto <xref:System.Drawing.Font> .  
  
 Nell'illustrazione seguente viene mostrato l'output del testo disegnato nel rettangolo quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> Metodo:
  
 ![Screenshot che mostra l'output quando si usa il metodo DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Per creare testo incapsulato in un rettangolo con GDI+  
  
1. Usare il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload, passando il testo desiderato, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> , <xref:System.Drawing.Font> e <xref:System.Drawing.Brush> .  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Per creare testo incapsulato in un rettangolo con GDI  
  
1. Usare il <xref:System.Windows.Forms.TextFormatFlags> valore di enumerazione per specificare che il testo deve essere incluso nel <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload, passando il testo desiderato, <xref:System.Drawing.Rectangle> <xref:System.Drawing.Font> e <xref:System.Drawing.Color> .  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti richiedono:  
  
- <xref:System.Windows.Forms.PaintEventArgs>`e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Creare tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
- [Procedura: Disegnare testo in una posizione specificata](how-to-draw-text-at-a-specified-location.md)
