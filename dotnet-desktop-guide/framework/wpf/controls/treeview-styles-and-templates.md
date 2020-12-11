---
title: Stili e modelli di TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: e3c5743b2afefb4abfac5d71c6f5ccd8281ce453
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961348"
---
# <a name="treeview-styles-and-templates"></a>Stili e modelli di TreeView
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.TreeView> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).  
  
## <a name="treeview-parts"></a>Parti TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo non dispone di parti denominate.  
  
 Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.TreeView> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.TreeView> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .  
  
## <a name="treeview-states"></a>Stati di TreeView  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.TreeView> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="treeviewitem-parts"></a>Parti TreeViewItem  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Elemento visivo che contiene il contenuto dell'intestazione del <xref:System.Windows.Controls.TreeView> controllo.|  
  
## <a name="treeviewitem-states"></a>Stati di TreeViewItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato su <xref:System.Windows.Controls.TreeViewItem> .|  
|Disabled|CommonStates|<xref:System.Windows.Controls.TreeViewItem>È disabilitato.|  
|Con stato attivo|FocusStates|<xref:System.Windows.Controls.TreeViewItem>Ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Non <xref:System.Windows.Controls.TreeViewItem> ha lo stato attivo.|  
|Esteso|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo è espanso.|  
|Collapsed|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo è compresso.|  
|HasItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem>Dispone di elementi.|  
|Noitems|HasItemsStates|Non <xref:System.Windows.Controls.TreeViewItem> contiene elementi.|  
|Opzione selezionata|SelectionStates|L'oggetto <xref:System.Windows.Controls.TreeViewItem> è selezionato.|  
|SelectedInactive|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionato ma non attivo.|  
|Deselezionato|SelectionStates|L'oggetto <xref:System.Windows.Controls.TreeViewItem> non è selezionato.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="treeview-controltemplate-example"></a>Esempio di ControlTemplate TreeView  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TreeView> controllo e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
