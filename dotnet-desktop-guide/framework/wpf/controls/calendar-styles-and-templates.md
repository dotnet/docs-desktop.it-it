---
title: Stili e modelli di Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 3639a6f012aae7e15bae0e765e46f92015273286
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967168"
---
# <a name="calendar-styles-and-templates"></a>Stili e modelli di Calendar
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Calendar> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).  
  
## <a name="calendar-parts"></a>Parti del calendario  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Calendar> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Mese o anno attualmente visualizzato nell'oggetto <xref:System.Windows.Controls.Calendar> .|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Pannello contenente l'oggetto <xref:System.Windows.Controls.Primitives.CalendarItem> .|  
  
## <a name="calendar-states"></a>Stati del calendario  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Calendar> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="calendaritem-parts"></a>Parti CalendarItem  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Radice del controllo.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Pulsante che visualizza la pagina precedente del calendario quando viene selezionato.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Pulsante che visualizza la pagina successiva del calendario quando viene selezionato.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Pulsante che consente di passare tra la modalità mese, la modalità anno e la modalità decade.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità mese.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità anno o decade.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Sovrapposizione per lo stato disabilitato.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|Oggetto <xref:System.Windows.DataTemplate> che descrive la struttura visiva.|  
  
## <a name="calendaritem-states"></a>Stati CalendarItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Stato normale|CommonStates|Lo stato predefinito.|  
|Stato disattivato|CommonStates|Stato del calendario quando la <xref:System.Windows.UIElement.IsEnabled%2A> proprietà è `false` .|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="calendardaybutton-parts"></a>Parti CalendarDayButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo non dispone di parti denominate.  
  
## <a name="calendardaybutton-states"></a>Stati CalendarDayButton  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>È disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato su <xref:System.Windows.Controls.Primitives.CalendarDayButton> .|  
|Premuto|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>Viene premuto.|  
|Opzione selezionata|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non ha lo stato attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non ha lo stato attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inactive|ActiveStates|Il pulsante è inattivo.|  
|RegularDay|DayStates|Il pulsante non rappresenta <xref:System.DateTime.Today%2A?displayProperty=nameWithType> .|  
|Oggi|DayStates|Il pulsante rappresenta <xref:System.DateTime.Today%2A?displayProperty=nameWithType> .|  
|NormalDay|BlackoutDayStates|Il pulsante rappresenta un giorno selezionabile.|  
|BlackoutDay|BlackoutDayStates|Il pulsante rappresenta un giorno che non può essere selezionato.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="calendarbutton-parts"></a>Parti CalendarButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarButton> controllo non dispone di parti denominate.  
  
## <a name="calendarbutton-states"></a>Stati CalendarButton  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.CalendarButton> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>È disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato su <xref:System.Windows.Controls.Primitives.CalendarButton> .|  
|Premuto|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>Viene premuto.|  
|Opzione selezionata|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non ha lo stato attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non ha lo stato attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inactive|ActiveStates|Il pulsante è inattivo.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="calendar-controltemplate-example"></a>Esempio di ControlTemplate del calendario  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Calendar> controllo e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
