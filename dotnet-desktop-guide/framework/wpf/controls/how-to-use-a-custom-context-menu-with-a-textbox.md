---
title: 'Procedura: utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 93ee6d44e9e5703d70d0583b759330a9e52f60b9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964801"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="320a2-102">Procedura: utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="320a2-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="320a2-103">Questo esempio illustra come definire e implementare un semplice menu di scelta rapida personalizzato per un oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="320a2-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="320a2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="320a2-104">Example</span></span>  
 <span data-ttu-id="320a2-105">Nell' [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene definito un <xref:System.Windows.Controls.TextBox> controllo che include un menu di scelta rapida personalizzato.</span><span class="sxs-lookup"><span data-stu-id="320a2-105">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="320a2-106">Il menu di scelta rapida viene definito utilizzando un <xref:System.Windows.Controls.ContextMenu> elemento.</span><span class="sxs-lookup"><span data-stu-id="320a2-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="320a2-107">Il menu di scelta rapida è costituito da una serie di <xref:System.Windows.Controls.MenuItem> elementi ed elementi <xref:System.Windows.Controls.Separator> .</span><span class="sxs-lookup"><span data-stu-id="320a2-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="320a2-108">Ogni <xref:System.Windows.Controls.MenuItem> elemento definisce un comando nel menu di scelta rapida <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> . l'attributo definisce il testo visualizzato per il comando di menu e l' <xref:System.Windows.Controls.MenuItem.Click> attributo specifica un metodo del gestore per ogni voce di menu.</span><span class="sxs-lookup"><span data-stu-id="320a2-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="320a2-109">L' <xref:System.Windows.Controls.Separator> elemento causa semplicemente il rendering di una linea di separazione tra le voci di menu precedenti e successive.</span><span class="sxs-lookup"><span data-stu-id="320a2-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="320a2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="320a2-110">Example</span></span>  
 <span data-ttu-id="320a2-111">Nell'esempio seguente viene illustrato il codice di implementazione per la definizione del menu di scelta rapida precedente, nonché il codice che Abilita e Disabilita il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="320a2-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="320a2-112">L' <xref:System.Windows.Controls.ContextMenu.Opened> evento viene utilizzato per abilitare o disabilitare in modo dinamico determinati comandi a seconda dello stato corrente di <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="320a2-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="320a2-113">Per ripristinare il menu di scelta rapida predefinito, utilizzare il <xref:System.Windows.DependencyObject.ClearValue%2A> metodo per cancellare il valore della <xref:System.Windows.FrameworkElement.ContextMenu%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="320a2-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="320a2-114">Per disabilitare completamente il menu di scelta rapida, impostare la <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà su un riferimento null ( `Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="320a2-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="320a2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="320a2-115">See also</span></span>

- [<span data-ttu-id="320a2-116">Usare il controllo ortografico con un menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="320a2-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="320a2-117">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="320a2-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="320a2-118">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="320a2-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
