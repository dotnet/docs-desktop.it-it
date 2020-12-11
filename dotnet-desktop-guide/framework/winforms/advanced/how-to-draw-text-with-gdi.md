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
# <a name="how-to-draw-text-with-gdi"></a>Procedura: Disegnare testo con GDI
Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo nella <xref:System.Windows.Forms.TextRenderer> classe, è possibile accedere alla funzionalità GDI per il disegno di testo in un form o un controllo. Il rendering del testo GDI offre in genere prestazioni migliori e una misurazione più accurata del testo rispetto a GDI+.  
  
> [!NOTE]
> I <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi della <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa. Quando si esegue la stampa, utilizzare sempre i <xref:System.Drawing.Graphics.DrawString%2A> metodi della <xref:System.Drawing.Graphics> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come creare testo su più righe all'interno di un rettangolo utilizzando il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Per eseguire il rendering del testo con la <xref:System.Windows.Forms.TextRenderer> classe, è necessario un oggetto <xref:System.Drawing.IDeviceContext> , ad esempio un oggetto <xref:System.Drawing.Graphics> e un oggetto <xref:System.Drawing.Font> , un percorso per disegnare il testo e il colore in cui deve essere disegnato. Facoltativamente, è possibile specificare la formattazione del testo utilizzando l' <xref:System.Windows.Forms.TextFormatFlags> enumerazione.  
  
 Per ulteriori informazioni su come ottenere un oggetto <xref:System.Drawing.Graphics> , vedere [procedura: creare oggetti grafici per il disegno](how-to-create-graphics-objects-for-drawing.md). Per altre informazioni sulla costruzione di un oggetto <xref:System.Drawing.Font> , vedere [procedura: costruire famiglie di caratteri e tipi](how-to-construct-font-families-and-fonts.md)di carattere.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio di codice precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
