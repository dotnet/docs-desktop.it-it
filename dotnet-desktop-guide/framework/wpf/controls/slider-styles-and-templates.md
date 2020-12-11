---
title: Stili e modelli di Slider
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: d97e9c1e2783d2c348955622fbe98ea3916726d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965977"
---
# <a name="slider-styles-and-templates"></a>Stili e modelli di Slider
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Slider> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).  
  
## <a name="slider-parts"></a>Parti del dispositivo di scorrimento  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Slider> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|Contenitore per l'elemento che indica la posizione dell'oggetto <xref:System.Windows.Controls.Slider> .|  
|PART_SelectionRange|<xref:System.Windows.FrameworkElement>|Elemento che visualizza un intervallo di selezione lungo <xref:System.Windows.Controls.Slider> .  L'intervallo di selezione è visibile solo se la <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> proprietà è `true` .|  
  
## <a name="slider-states"></a>Stati del dispositivo di scorrimento  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Slider> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Disabled|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="slider-controltemplate-example"></a>Esempio di ControlTemplate Slider  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Slider> controllo.  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
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
