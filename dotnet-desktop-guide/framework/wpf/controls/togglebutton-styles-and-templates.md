---
title: Stili e modelli di ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 2c5aee58878ea6199c07ee201882fd3ded97bdee
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965956"
---
# <a name="togglebutton-styles-and-templates"></a>Stili e modelli di ToggleButton

In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).

## <a name="togglebutton-parts"></a>Parti ToggleButton

Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.

## <a name="togglebutton-states"></a>Stati di ToggleButton

Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.

|Nome VisualState|Nome VisualStateGroup|Descrizione|
|-|-|-|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Premuto|CommonStates|Il controllo è premuto.|
|Disabled|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|
|Selezionata|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.|
|Non selezionato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.|
|Indeterminato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> è `true` e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.|
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|

> [!NOTE]
> Se lo stato di visualizzazione indeterminato non esiste nel modello di controllo, lo stato di visualizzazione non verificato verrà usato come stato di visualizzazione predefinito.

## <a name="togglebutton-controltemplate-example"></a>Esempio di ControlTemplate ControlTemplate

Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

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
