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
# <a name="how-to-align-drawn-text"></a>Procedura: Allineare il testo disegnato
Quando si esegue un disegno personalizzato, è spesso consigliabile centrare il testo disegnato su un form o un controllo. È possibile allineare facilmente il testo disegnato con <xref:System.Drawing.Graphics.DrawString%2A> i <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi o creando l'oggetto di formattazione corretto e impostando i flag di formato appropriati.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Per creare il testo centrato con GDI+ (DrawString)  
  
1. Usare un <xref:System.Drawing.StringFormat> con il <xref:System.Drawing.Graphics.DrawString%2A> metodo appropriato per specificare il testo centrato.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Per creare il testo centrato con GDI (DrawText)  
  
1. Usare l' <xref:System.Windows.Forms.TextFormatFlags> enumerazione per il wrapping e il testo centrato verticalmente e orizzontalmente con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo appropriato.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi di codice precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Disegnare testo con GDI](how-to-draw-text-with-gdi.md)
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Creare tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)
