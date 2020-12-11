---
title: Stili e modelli di StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 6b56ff468a195aaac470eaa944af481086e87520
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962779"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="449e0-102">Stili e modelli di StatusBar</span><span class="sxs-lookup"><span data-stu-id="449e0-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="449e0-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="449e0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="449e0-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="449e0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="449e0-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="449e0-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="449e0-106">Parti StatusBar</span><span class="sxs-lookup"><span data-stu-id="449e0-106">StatusBar Parts</span></span>  
 <span data-ttu-id="449e0-107">Il <xref:System.Windows.Controls.Primitives.StatusBar> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="449e0-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="449e0-108">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="449e0-108">StatusBar States</span></span>  
 <span data-ttu-id="449e0-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="449e0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="449e0-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="449e0-110">VisualState Name</span></span>|<span data-ttu-id="449e0-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="449e0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="449e0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="449e0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="449e0-113">Valido</span><span class="sxs-lookup"><span data-stu-id="449e0-113">Valid</span></span>|<span data-ttu-id="449e0-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-114">ValidationStates</span></span>|<span data-ttu-id="449e0-115">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="449e0-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="449e0-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="449e0-116">InvalidFocused</span></span>|<span data-ttu-id="449e0-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-117">ValidationStates</span></span>|<span data-ttu-id="449e0-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="449e0-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="449e0-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="449e0-119">InvalidUnfocused</span></span>|<span data-ttu-id="449e0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-120">ValidationStates</span></span>|<span data-ttu-id="449e0-121">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="449e0-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="449e0-122">Parti StatusBarItem</span><span class="sxs-lookup"><span data-stu-id="449e0-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="449e0-123">Il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="449e0-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="449e0-124">Stati di StatusBar</span><span class="sxs-lookup"><span data-stu-id="449e0-124">StatusBar States</span></span>  
 <span data-ttu-id="449e0-125">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.StatusBarItem> controllo.</span><span class="sxs-lookup"><span data-stu-id="449e0-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="449e0-126">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="449e0-126">VisualState Name</span></span>|<span data-ttu-id="449e0-127">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="449e0-127">VisualStateGroup Name</span></span>|<span data-ttu-id="449e0-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="449e0-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="449e0-129">Valido</span><span class="sxs-lookup"><span data-stu-id="449e0-129">Valid</span></span>|<span data-ttu-id="449e0-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-130">ValidationStates</span></span>|<span data-ttu-id="449e0-131">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="449e0-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="449e0-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="449e0-132">InvalidFocused</span></span>|<span data-ttu-id="449e0-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-133">ValidationStates</span></span>|<span data-ttu-id="449e0-134">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="449e0-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="449e0-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="449e0-135">InvalidUnfocused</span></span>|<span data-ttu-id="449e0-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="449e0-136">ValidationStates</span></span>|<span data-ttu-id="449e0-137">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="449e0-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="449e0-138">Esempio di ControlTemplate StatusBar</span><span class="sxs-lookup"><span data-stu-id="449e0-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="449e0-139">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="449e0-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="449e0-140"><xref:System.Windows.Controls.ControlTemplate>Usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="449e0-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="449e0-141">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="449e0-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="449e0-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="449e0-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="449e0-143">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="449e0-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="449e0-144">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="449e0-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="449e0-145">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="449e0-145">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="449e0-146">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="449e0-146">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
