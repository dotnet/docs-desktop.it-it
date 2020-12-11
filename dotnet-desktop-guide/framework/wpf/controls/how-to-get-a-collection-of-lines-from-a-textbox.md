---
title: 'Procedura: ottenere una raccolta di righe da un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967351"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Procedura: ottenere una raccolta di righe da un controllo TextBox
Questo esempio illustra come ottenere una raccolta di righe di testo da un oggetto <xref:System.Windows.Controls.TextBox> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un metodo semplice che accetta <xref:System.Windows.Controls.TextBox> come argomento e restituisce un oggetto <xref:System.Collections.Specialized.StringCollection> contenente le righe di testo nella **casella** di testo.  La <xref:System.Windows.Controls.TextBox.LineCount%2A> proprietà viene utilizzata per determinare il numero di righe attualmente presenti nella **casella di testo** e il <xref:System.Windows.Controls.TextBox.GetLineText%2A> metodo viene quindi utilizzato per estrarre ogni riga e aggiungerla alla raccolta di righe.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
