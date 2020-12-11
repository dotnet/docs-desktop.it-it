---
title: Stili e modelli di PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: aecd625a052f097aeb2b8cb73743fd4b47df89e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951809"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="92a80-102">Stili e modelli di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="92a80-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="92a80-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="92a80-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="92a80-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="92a80-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="92a80-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="92a80-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="92a80-106">Parti PasswordBox</span><span class="sxs-lookup"><span data-stu-id="92a80-106">PasswordBox Parts</span></span>

<span data-ttu-id="92a80-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="92a80-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="92a80-108">Parte</span><span class="sxs-lookup"><span data-stu-id="92a80-108">Part</span></span>|<span data-ttu-id="92a80-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="92a80-109">Type</span></span>|<span data-ttu-id="92a80-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92a80-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="92a80-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="92a80-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="92a80-112">Elemento visivo che può contenere un oggetto <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="92a80-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="92a80-113">Il testo di <xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="92a80-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="92a80-114">Stati di PasswordBox</span><span class="sxs-lookup"><span data-stu-id="92a80-114">PasswordBox States</span></span>

<span data-ttu-id="92a80-115">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="92a80-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="92a80-116">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="92a80-116">VisualState Name</span></span>|<span data-ttu-id="92a80-117">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="92a80-117">VisualStateGroup Name</span></span>|<span data-ttu-id="92a80-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92a80-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="92a80-119">Normale</span><span class="sxs-lookup"><span data-stu-id="92a80-119">Normal</span></span>|<span data-ttu-id="92a80-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="92a80-120">CommonStates</span></span>|<span data-ttu-id="92a80-121">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="92a80-121">The default state.</span></span>|
|<span data-ttu-id="92a80-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="92a80-122">MouseOver</span></span>|<span data-ttu-id="92a80-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="92a80-123">CommonStates</span></span>|<span data-ttu-id="92a80-124">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="92a80-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="92a80-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="92a80-125">Disabled</span></span>|<span data-ttu-id="92a80-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="92a80-126">CommonStates</span></span>|<span data-ttu-id="92a80-127">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="92a80-127">The control is disabled.</span></span>|
|<span data-ttu-id="92a80-128">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="92a80-128">Focused</span></span>|<span data-ttu-id="92a80-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="92a80-129">FocusStates</span></span>|<span data-ttu-id="92a80-130">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="92a80-130">The control has focus.</span></span>|
|<span data-ttu-id="92a80-131">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="92a80-131">Unfocused</span></span>|<span data-ttu-id="92a80-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="92a80-132">FocusStates</span></span>|<span data-ttu-id="92a80-133">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="92a80-133">The control does not have focus.</span></span>|
|<span data-ttu-id="92a80-134">Valido</span><span class="sxs-lookup"><span data-stu-id="92a80-134">Valid</span></span>|<span data-ttu-id="92a80-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="92a80-135">ValidationStates</span></span>|<span data-ttu-id="92a80-136">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="92a80-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="92a80-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="92a80-137">InvalidFocused</span></span>|<span data-ttu-id="92a80-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="92a80-138">ValidationStates</span></span>|<span data-ttu-id="92a80-139">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="92a80-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="92a80-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="92a80-140">InvalidUnfocused</span></span>|<span data-ttu-id="92a80-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="92a80-141">ValidationStates</span></span>|<span data-ttu-id="92a80-142">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="92a80-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="92a80-143">Esempio di ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="92a80-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="92a80-144">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.PasswordBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="92a80-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="92a80-145">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="92a80-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="92a80-146">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="92a80-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="92a80-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92a80-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="92a80-148">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="92a80-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="92a80-149">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="92a80-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="92a80-150">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="92a80-150">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="92a80-151">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="92a80-151">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
