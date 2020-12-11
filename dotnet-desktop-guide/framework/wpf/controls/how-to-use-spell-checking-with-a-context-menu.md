---
title: 'Procedura: utilizzare il controllo ortografico con un menu di scelta rapida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 0c2ceb3e4091ee1d98bd0c786f51b3596cdedd08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951881"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Procedura: utilizzare il controllo ortografico con un menu di scelta rapida
Per impostazione predefinita, quando si Abilita il controllo ortografico in un controllo di modifica <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> , ad esempio o, si ottengono scelte di controllo ortografico nel menu di scelta rapida. Ad esempio, quando gli utenti fanno clic con il pulsante destro del mouse su una parola digitata in modo errato, ricevono un set di suggerimenti ortografici o l'opzione per **ignorarli tutti**. Tuttavia, quando si sostituisce il menu di scelta rapida predefinito con il menu di scelta rapida personalizzato, questa funzionalità viene persa ed è necessario scrivere il codice per riabilitare la funzionalità di controllo ortografico nel menu di scelta rapida. Nell'esempio seguente viene illustrato come abilitare questa operazione su un oggetto <xref:System.Windows.Controls.TextBox> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'oggetto [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] che crea un oggetto <xref:System.Windows.Controls.TextBox> con alcuni eventi utilizzati per implementare il menu di scelta rapida.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice che implementa il menu di scelta rapida.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Il codice utilizzato per eseguire questa operazione con un <xref:System.Windows.Controls.RichTextBox> è simile. La differenza principale è rappresentata dal parametro passato al `GetSpellingError` metodo. Per un <xref:System.Windows.Controls.TextBox> , passare l'indice Integer della posizione del punto di inserimento:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Per un oggetto <xref:System.Windows.Controls.RichTextBox> , passare l'oggetto <xref:System.Windows.Documents.TextPointer> che specifica la posizione del punto di inserimento:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
- [Attivare il controllo ortografico in un controllo di modifica del testo](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [Usare un menu di scelta rapida personalizzato con un oggetto TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md)
