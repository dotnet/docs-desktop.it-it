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
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="89e77-102">Procedura: utilizzare il controllo ortografico con un menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="89e77-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="89e77-103">Per impostazione predefinita, quando si Abilita il controllo ortografico in un controllo di modifica <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> , ad esempio o, si ottengono scelte di controllo ortografico nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="89e77-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="89e77-104">Ad esempio, quando gli utenti fanno clic con il pulsante destro del mouse su una parola digitata in modo errato, ricevono un set di suggerimenti ortografici o l'opzione per **ignorarli tutti**.</span><span class="sxs-lookup"><span data-stu-id="89e77-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="89e77-105">Tuttavia, quando si sostituisce il menu di scelta rapida predefinito con il menu di scelta rapida personalizzato, questa funzionalità viene persa ed è necessario scrivere il codice per riabilitare la funzionalità di controllo ortografico nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="89e77-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="89e77-106">Nell'esempio seguente viene illustrato come abilitare questa operazione su un oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="89e77-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89e77-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="89e77-107">Example</span></span>  
 <span data-ttu-id="89e77-108">Nell'esempio seguente viene illustrato l'oggetto [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] che crea un oggetto <xref:System.Windows.Controls.TextBox> con alcuni eventi utilizzati per implementare il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="89e77-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="89e77-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="89e77-109">Example</span></span>  
 <span data-ttu-id="89e77-110">Nell'esempio seguente viene illustrato il codice che implementa il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="89e77-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="89e77-111">Il codice utilizzato per eseguire questa operazione con un <xref:System.Windows.Controls.RichTextBox> è simile.</span><span class="sxs-lookup"><span data-stu-id="89e77-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="89e77-112">La differenza principale è rappresentata dal parametro passato al `GetSpellingError` metodo.</span><span class="sxs-lookup"><span data-stu-id="89e77-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="89e77-113">Per un <xref:System.Windows.Controls.TextBox> , passare l'indice Integer della posizione del punto di inserimento:</span><span class="sxs-lookup"><span data-stu-id="89e77-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="89e77-114">Per un oggetto <xref:System.Windows.Controls.RichTextBox> , passare l'oggetto <xref:System.Windows.Documents.TextPointer> che specifica la posizione del punto di inserimento:</span><span class="sxs-lookup"><span data-stu-id="89e77-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="89e77-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89e77-115">See also</span></span>

- [<span data-ttu-id="89e77-116">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="89e77-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="89e77-117">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="89e77-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="89e77-118">Attivare il controllo ortografico in un controllo di modifica del testo</span><span class="sxs-lookup"><span data-stu-id="89e77-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="89e77-119">Usare un menu di scelta rapida personalizzato con un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="89e77-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
