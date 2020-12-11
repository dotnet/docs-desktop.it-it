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
# <a name="how-to-draw-text-at-a-specified-location"></a>Procedura: Disegnare testo in una posizione specificata
Quando si esegue un disegno personalizzato, è possibile tracciare il testo in un'unica riga orizzontale a partire da un punto specificato. È possibile creare il testo in questo modo utilizzando il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload della <xref:System.Drawing.Graphics> classe che accetta un <xref:System.Drawing.Point> <xref:System.Drawing.PointF> parametro o. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo richiede anche un <xref:System.Drawing.Brush> e <xref:System.Drawing.Font>  
  
 È anche possibile usare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo di overload di <xref:System.Windows.Forms.TextRenderer> che accetta un oggetto <xref:System.Drawing.Point> . <xref:System.Windows.Forms.TextRenderer.DrawText%2A> richiede anche un oggetto <xref:System.Drawing.Color> e un oggetto <xref:System.Drawing.Font> .  
  
 La figura seguente mostra l'output del testo disegnato in un punto specificato quando si usa il <xref:System.Drawing.Graphics.DrawString%2A> metodo di overload.  
  
 ![Screenshot che mostra l'output del testo in corrispondenza di un punto specificato.](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per creare una riga di testo con GDI+  
  
1. Usare il <xref:System.Drawing.Graphics.DrawString%2A> metodo, passando il testo desiderato, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> , <xref:System.Drawing.Font> e <xref:System.Drawing.Brush> .  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Per creare una riga di testo con GDI  
  
1. Usare il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo, passando il testo desiderato,, <xref:System.Drawing.Point> <xref:System.Drawing.Font> e <xref:System.Drawing.Color> .  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti richiedono:  
  
- <xref:System.Windows.Forms.PaintEventArgs>  `e`, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Creare tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
- [Procedura: Disegnare testo disposto su più righe in un rettangolo](how-to-draw-wrapped-text-in-a-rectangle.md)
