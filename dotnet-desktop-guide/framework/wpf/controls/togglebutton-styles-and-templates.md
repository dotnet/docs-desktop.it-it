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
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="a10a4-102">Stili e modelli di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="a10a4-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="a10a4-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="a10a4-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="a10a4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a10a4-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="a10a4-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="a10a4-106">Parti ToggleButton</span><span class="sxs-lookup"><span data-stu-id="a10a4-106">ToggleButton Parts</span></span>

<span data-ttu-id="a10a4-107">Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="a10a4-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="a10a4-108">Stati di ToggleButton</span><span class="sxs-lookup"><span data-stu-id="a10a4-108">ToggleButton States</span></span>

<span data-ttu-id="a10a4-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="a10a4-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="a10a4-110">VisualState Name</span></span>|<span data-ttu-id="a10a4-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a10a4-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a10a4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a10a4-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="a10a4-113">Normale</span><span class="sxs-lookup"><span data-stu-id="a10a4-113">Normal</span></span>|<span data-ttu-id="a10a4-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-114">CommonStates</span></span>|<span data-ttu-id="a10a4-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="a10a4-115">The default state.</span></span>|
|<span data-ttu-id="a10a4-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a10a4-116">MouseOver</span></span>|<span data-ttu-id="a10a4-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-117">CommonStates</span></span>|<span data-ttu-id="a10a4-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="a10a4-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="a10a4-119">Pressed</span></span>|<span data-ttu-id="a10a4-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-120">CommonStates</span></span>|<span data-ttu-id="a10a4-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="a10a4-121">The control is pressed.</span></span>|
|<span data-ttu-id="a10a4-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="a10a4-122">Disabled</span></span>|<span data-ttu-id="a10a4-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-123">CommonStates</span></span>|<span data-ttu-id="a10a4-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a10a4-124">The control is disabled.</span></span>|
|<span data-ttu-id="a10a4-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="a10a4-125">Focused</span></span>|<span data-ttu-id="a10a4-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-126">FocusStates</span></span>|<span data-ttu-id="a10a4-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-127">The control has focus.</span></span>|
|<span data-ttu-id="a10a4-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="a10a4-128">Unfocused</span></span>|<span data-ttu-id="a10a4-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-129">FocusStates</span></span>|<span data-ttu-id="a10a4-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-130">The control does not have focus.</span></span>|
|<span data-ttu-id="a10a4-131">Selezionata</span><span class="sxs-lookup"><span data-stu-id="a10a4-131">Checked</span></span>|<span data-ttu-id="a10a4-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-132">CheckStates</span></span>|<span data-ttu-id="a10a4-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="a10a4-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="a10a4-134">Non selezionato</span><span class="sxs-lookup"><span data-stu-id="a10a4-134">Unchecked</span></span>|<span data-ttu-id="a10a4-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-135">CheckStates</span></span>|<span data-ttu-id="a10a4-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="a10a4-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="a10a4-137">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="a10a4-137">Indeterminate</span></span>|<span data-ttu-id="a10a4-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-138">CheckStates</span></span>|<span data-ttu-id="a10a4-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> è `true` e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.</span><span class="sxs-lookup"><span data-stu-id="a10a4-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="a10a4-140">Valido</span><span class="sxs-lookup"><span data-stu-id="a10a4-140">Valid</span></span>|<span data-ttu-id="a10a4-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-141">ValidationStates</span></span>|<span data-ttu-id="a10a4-142">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="a10a4-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="a10a4-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a10a4-143">InvalidFocused</span></span>|<span data-ttu-id="a10a4-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-144">ValidationStates</span></span>|<span data-ttu-id="a10a4-145">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="a10a4-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a10a4-146">InvalidUnfocused</span></span>|<span data-ttu-id="a10a4-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a10a4-147">ValidationStates</span></span>|<span data-ttu-id="a10a4-148">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="a10a4-149">Se lo stato di visualizzazione indeterminato non esiste nel modello di controllo, lo stato di visualizzazione non verificato verrà usato come stato di visualizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="a10a4-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="a10a4-150">Esempio di ControlTemplate ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a10a4-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="a10a4-151">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="a10a4-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="a10a4-152">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="a10a4-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="a10a4-153">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a10a4-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="a10a4-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a10a4-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a10a4-155">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="a10a4-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a10a4-156">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="a10a4-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a10a4-157">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a10a4-157">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="a10a4-158">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="a10a4-158">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
