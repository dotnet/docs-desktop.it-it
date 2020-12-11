---
title: Stili e modelli di Button
description: Informazioni sugli stili e i modelli per il controllo pulsante Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 957c0663a8c444de71d2710bcff04cb73aaf3e27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967186"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="87e33-104">Stili e modelli di Button</span><span class="sxs-lookup"><span data-stu-id="87e33-104">Button Styles and Templates</span></span>
<span data-ttu-id="87e33-105">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e33-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="87e33-106">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="87e33-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="87e33-107">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="87e33-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="87e33-108">Parti del pulsante</span><span class="sxs-lookup"><span data-stu-id="87e33-108">Button Parts</span></span>  
 <span data-ttu-id="87e33-109">Il <xref:System.Windows.Controls.Button> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="87e33-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="87e33-110">Stati del pulsante</span><span class="sxs-lookup"><span data-stu-id="87e33-110">Button States</span></span>  
 <span data-ttu-id="87e33-111">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e33-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="87e33-112">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="87e33-112">VisualState Name</span></span>|<span data-ttu-id="87e33-113">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="87e33-113">VisualStateGroup Name</span></span>|<span data-ttu-id="87e33-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87e33-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="87e33-115">Normale</span><span class="sxs-lookup"><span data-stu-id="87e33-115">Normal</span></span>|<span data-ttu-id="87e33-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="87e33-116">CommonStates</span></span>|<span data-ttu-id="87e33-117">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="87e33-117">The default state.</span></span>|  
|<span data-ttu-id="87e33-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="87e33-118">MouseOver</span></span>|<span data-ttu-id="87e33-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="87e33-119">CommonStates</span></span>|<span data-ttu-id="87e33-120">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="87e33-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="87e33-121">Premuto</span><span class="sxs-lookup"><span data-stu-id="87e33-121">Pressed</span></span>|<span data-ttu-id="87e33-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="87e33-122">CommonStates</span></span>|<span data-ttu-id="87e33-123">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="87e33-123">The control is pressed.</span></span>|  
|<span data-ttu-id="87e33-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="87e33-124">Disabled</span></span>|<span data-ttu-id="87e33-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="87e33-125">CommonStates</span></span>|<span data-ttu-id="87e33-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="87e33-126">The control is disabled.</span></span>|  
|<span data-ttu-id="87e33-127">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="87e33-127">Focused</span></span>|<span data-ttu-id="87e33-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="87e33-128">FocusStates</span></span>|<span data-ttu-id="87e33-129">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="87e33-129">The control has focus.</span></span>|  
|<span data-ttu-id="87e33-130">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="87e33-130">Unfocused</span></span>|<span data-ttu-id="87e33-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="87e33-131">FocusStates</span></span>|<span data-ttu-id="87e33-132">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="87e33-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="87e33-133">Valido</span><span class="sxs-lookup"><span data-stu-id="87e33-133">Valid</span></span>|<span data-ttu-id="87e33-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e33-134">ValidationStates</span></span>|<span data-ttu-id="87e33-135">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="87e33-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="87e33-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="87e33-136">InvalidFocused</span></span>|<span data-ttu-id="87e33-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e33-137">ValidationStates</span></span>|<span data-ttu-id="87e33-138">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="87e33-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="87e33-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="87e33-139">InvalidUnfocused</span></span>|<span data-ttu-id="87e33-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87e33-140">ValidationStates</span></span>|<span data-ttu-id="87e33-141">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="87e33-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="87e33-142">Esempio di ControlTemplate Button</span><span class="sxs-lookup"><span data-stu-id="87e33-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="87e33-143">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="87e33-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="87e33-144">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="87e33-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="87e33-145">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="87e33-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e33-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87e33-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="87e33-147">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="87e33-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="87e33-148">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="87e33-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="87e33-149">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="87e33-149">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="87e33-150">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="87e33-150">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
