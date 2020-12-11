---
title: "Procedura: posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox"
description: Informazioni su come posizionare il cursore all'inizio o alla fine del contenuto di testo di un controllo TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 32a738c37bac07e660fe84e3707ba4352594928a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968263"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>Procedura: posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox
In questo esempio viene illustrato come posizionare il cursore all'inizio o alla fine del contenuto di testo di un <xref:System.Windows.Controls.TextBox> controllo.  
  
## <a name="example"></a>Esempio  
 Nel [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice seguente viene descritto un <xref:System.Windows.Controls.TextBox> controllo a cui viene assegnato un nome.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Esempio  
 Per posizionare il cursore all'inizio del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> metodo e specificare la posizione iniziale della selezione 0 e una lunghezza di selezione pari a 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Esempio  
 Per posizionare il cursore alla fine del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> metodo e specificare la posizione iniziale della selezione uguale alla lunghezza del contenuto di testo e una lunghezza di selezione pari a 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
