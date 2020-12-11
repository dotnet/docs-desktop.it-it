---
title: "Procedura: Usare l'antialiasing nel testo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963214"
---
# <a name="how-to-use-antialiasing-with-text"></a>Procedura: Usare l'antialiasing nel testo
L' *anti-aliasing* si riferisce alla smussatura dei bordi frastagliati della grafica e del testo disegnati per migliorarne l'aspetto o la leggibilità. Con le classi GDI+ gestite, è possibile eseguire il rendering di testo con antialiasing di alta qualità, oltre a testo di qualità inferiore. In genere, il rendering di qualità superiore impiega più tempo di elaborazione rispetto al rendering di qualità inferiore. Per impostare il livello di qualità del testo, impostare la <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> su uno degli elementi dell' <xref:System.Drawing.Text.TextRenderingHint> enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene disegnato testo con due diverse impostazioni di qualità.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 Nella figura seguente viene illustrato l'output del codice di esempio:  
  
 ![Screenshot che mostra il testo con due diverse impostazioni di qualità.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio di codice precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
