---
title: Stili e modelli di ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 781c185e01621767a82ebee054c578ed291c9b79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966151"
---
# <a name="progressbar-styles-and-templates"></a>Stili e modelli di ProgressBar
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ProgressBar> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).  
  
## <a name="progressbar-parts"></a>Parti ProgressBar  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.ProgressBar> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|Oggetto che indica lo stato di avanzamento.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|Oggetto che definisce il percorso dell'indicatore di stato.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Oggetto che abbellisce l'indicatore di stato.|  
  
## <a name="progressbar-states"></a>Stati ProgressBar  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.ProgressBar> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Determinato|CommonStates|<xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento in base alla <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Proprietà.|  
|Indeterminato|CommonStates|<xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento generico con un modello ripetuto.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="progressbar-controltemplate-example"></a>Esempio di ControlTemplate di ProgressBar  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ProgressBar> controllo.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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
