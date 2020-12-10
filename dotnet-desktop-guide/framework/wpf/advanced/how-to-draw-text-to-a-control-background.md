---
title: 'Procedura: creare testo sullo sfondo di un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951006"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>Procedura: creare testo sullo sfondo di un controllo
È possibile disegnare il testo direttamente sullo sfondo di un controllo convertendo una stringa di testo in un <xref:System.Windows.Media.FormattedText> oggetto e quindi disegnando l'oggetto nell'oggetto del controllo <xref:System.Windows.Media.DrawingContext> . È anche possibile usare questa tecnica per disegnare sullo sfondo degli oggetti derivati da <xref:System.Windows.Controls.Panel> , ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.StackPanel> .  
  
 ![Screenshot dei controlli che visualizzano testo come sfondo.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
Esempio di controlli con sfondi di testo personalizzati  
  
## <a name="example"></a>Esempio  
 Per creare uno sfondo di un controllo, creare un nuovo <xref:System.Windows.Media.DrawingBrush> oggetto e trascinare il testo convertito nell'oggetto <xref:System.Windows.Media.DrawingContext> . Quindi, assegnare il nuovo oggetto <xref:System.Windows.Media.DrawingBrush> alla proprietà background del controllo.  
  
 Nell'esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e come eseguire il progetto sullo sfondo di un <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button> oggetto e.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- [Disegno di testo formattato](drawing-formatted-text.md)
