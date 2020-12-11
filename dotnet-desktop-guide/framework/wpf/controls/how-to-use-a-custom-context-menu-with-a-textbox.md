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
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Procedura: utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox
Questo esempio illustra come definire e implementare un semplice menu di scelta rapida personalizzato per un oggetto <xref:System.Windows.Controls.TextBox> .  
  
## <a name="example"></a>Esempio  
 Nell' [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene definito un <xref:System.Windows.Controls.TextBox> controllo che include un menu di scelta rapida personalizzato.  
  
 Il menu di scelta rapida viene definito utilizzando un <xref:System.Windows.Controls.ContextMenu> elemento.  Il menu di scelta rapida è costituito da una serie di <xref:System.Windows.Controls.MenuItem> elementi ed elementi <xref:System.Windows.Controls.Separator> .  Ogni <xref:System.Windows.Controls.MenuItem> elemento definisce un comando nel menu di scelta rapida <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> . l'attributo definisce il testo visualizzato per il comando di menu e l' <xref:System.Windows.Controls.MenuItem.Click> attributo specifica un metodo del gestore per ogni voce di menu.  L' <xref:System.Windows.Controls.Separator> elemento causa semplicemente il rendering di una linea di separazione tra le voci di menu precedenti e successive.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice di implementazione per la definizione del menu di scelta rapida precedente, nonché il codice che Abilita e Disabilita il menu di scelta rapida.  L' <xref:System.Windows.Controls.ContextMenu.Opened> evento viene utilizzato per abilitare o disabilitare in modo dinamico determinati comandi a seconda dello stato corrente di <xref:System.Windows.Controls.TextBox> .  
  
 Per ripristinare il menu di scelta rapida predefinito, utilizzare il <xref:System.Windows.DependencyObject.ClearValue%2A> metodo per cancellare il valore della <xref:System.Windows.FrameworkElement.ContextMenu%2A> Proprietà.  Per disabilitare completamente il menu di scelta rapida, impostare la <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà su un riferimento null ( `Nothing` in Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>Vedere anche

- [Usare il controllo ortografico con un menu di scelta rapida](how-to-use-spell-checking-with-a-context-menu.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
