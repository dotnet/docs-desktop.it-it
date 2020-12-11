---
title: Stili e modelli di DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: c6663ae3f7f4eefc61c1a07d968ea300a485e157
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967549"
---
# <a name="datepicker-styles-and-templates"></a>Stili e modelli di DatePicker
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.DatePicker> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).  
  
## <a name="datepicker-parts"></a>Parti DatePicker  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.DatePicker> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Radice del controllo.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Pulsante che apre e chiude <xref:System.Windows.Controls.Calendar> .|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Casella di testo che consente di immettere una data.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Popup del <xref:System.Windows.Controls.DatePicker> controllo.|  
  
## <a name="datepicker-states"></a>Stati DatePicker  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.DatePicker> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.DatePicker>È disabilitato.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="datepickertextbox-parts"></a>Parti DatePickerTextBox  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Elemento che contiene il testo iniziale in <xref:System.Windows.Controls.DatePicker> .|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Elemento visivo che può contenere un oggetto <xref:System.Windows.FrameworkElement> . Il testo di <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.|  
  
## <a name="datepickertextbox-states"></a>Stati DatePickerTextBox  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>È disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato su <xref:System.Windows.Controls.Primitives.DatePickerTextBox> .|  
|ReadOnly|CommonStates|L'utente non può modificare il testo in <xref:System.Windows.Controls.Primitives.DatePickerTextBox> .|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Filigranata|WatermarkStates|Il controllo Visualizza il testo iniziale.  <xref:System.Windows.Controls.Primitives.DatePickerTextBox>Si trova nello stato quando l'utente non ha immesso il testo o ha selezionato una data.|  
|Con filigrana|WatermarkStates|L'utente ha immesso il testo in <xref:System.Windows.Controls.Primitives.DatePickerTextBox> o ha selezionato una data in <xref:System.Windows.Controls.DatePicker> .|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|  
  
## <a name="datepicker-controltemplate-example"></a>Esempio di ControlTemplate DatePicker  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DatePicker> controllo.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
