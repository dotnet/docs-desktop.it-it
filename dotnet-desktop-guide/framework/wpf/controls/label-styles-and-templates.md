---
title: Stili e modelli di Label
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: 476f10a11c497633e2650403068576633d517937
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967084"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="05621-102">Stili e modelli di Label</span><span class="sxs-lookup"><span data-stu-id="05621-102">Label Styles and Templates</span></span>
<span data-ttu-id="05621-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="05621-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="05621-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="05621-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="05621-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="05621-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="05621-106">Parti etichetta</span><span class="sxs-lookup"><span data-stu-id="05621-106">Label Parts</span></span>  
 <span data-ttu-id="05621-107">Il <xref:System.Windows.Controls.Label> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="05621-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="05621-108">Stati etichetta</span><span class="sxs-lookup"><span data-stu-id="05621-108">Label States</span></span>  
 <span data-ttu-id="05621-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="05621-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="05621-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="05621-110">VisualState Name</span></span>|<span data-ttu-id="05621-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="05621-111">VisualStateGroup Name</span></span>|<span data-ttu-id="05621-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05621-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="05621-113">Valido</span><span class="sxs-lookup"><span data-stu-id="05621-113">Valid</span></span>|<span data-ttu-id="05621-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="05621-114">ValidationStates</span></span>|<span data-ttu-id="05621-115">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="05621-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="05621-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="05621-116">InvalidFocused</span></span>|<span data-ttu-id="05621-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="05621-117">ValidationStates</span></span>|<span data-ttu-id="05621-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="05621-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="05621-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="05621-119">InvalidUnfocused</span></span>|<span data-ttu-id="05621-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="05621-120">ValidationStates</span></span>|<span data-ttu-id="05621-121">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="05621-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="05621-122">Esempio di ControlTemplate label</span><span class="sxs-lookup"><span data-stu-id="05621-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="05621-123">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Label> controllo.</span><span class="sxs-lookup"><span data-stu-id="05621-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="05621-124"><xref:System.Windows.Controls.ControlTemplate>Usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="05621-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="05621-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="05621-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05621-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05621-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="05621-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="05621-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="05621-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="05621-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="05621-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="05621-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="05621-130">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="05621-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
