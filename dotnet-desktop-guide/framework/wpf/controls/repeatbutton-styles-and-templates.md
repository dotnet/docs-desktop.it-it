---
title: Stili e modelli di RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: cff73c4c7ff06ad6d7b602ff1c6b9b38a4396509
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968902"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="08edc-102">Stili e modelli di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="08edc-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="08edc-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="08edc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="08edc-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="08edc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="08edc-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="08edc-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="08edc-106">Parti RepeatButton</span><span class="sxs-lookup"><span data-stu-id="08edc-106">RepeatButton Parts</span></span>

<span data-ttu-id="08edc-107">Il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="08edc-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="08edc-108">Stati di RepeatButton</span><span class="sxs-lookup"><span data-stu-id="08edc-108">RepeatButton States</span></span>

<span data-ttu-id="08edc-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="08edc-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="08edc-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="08edc-110">VisualState Name</span></span>|<span data-ttu-id="08edc-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="08edc-111">VisualStateGroup Name</span></span>|<span data-ttu-id="08edc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08edc-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="08edc-113">Normale</span><span class="sxs-lookup"><span data-stu-id="08edc-113">Normal</span></span>|<span data-ttu-id="08edc-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08edc-114">CommonStates</span></span>|<span data-ttu-id="08edc-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="08edc-115">The default state.</span></span>|
|<span data-ttu-id="08edc-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="08edc-116">MouseOver</span></span>|<span data-ttu-id="08edc-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08edc-117">CommonStates</span></span>|<span data-ttu-id="08edc-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="08edc-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="08edc-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="08edc-119">Pressed</span></span>|<span data-ttu-id="08edc-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08edc-120">CommonStates</span></span>|<span data-ttu-id="08edc-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="08edc-121">The control is pressed.</span></span>|
|<span data-ttu-id="08edc-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="08edc-122">Disabled</span></span>|<span data-ttu-id="08edc-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="08edc-123">CommonStates</span></span>|<span data-ttu-id="08edc-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="08edc-124">The control is disabled.</span></span>|
|<span data-ttu-id="08edc-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="08edc-125">Focused</span></span>|<span data-ttu-id="08edc-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08edc-126">FocusStates</span></span>|<span data-ttu-id="08edc-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="08edc-127">The control has focus.</span></span>|
|<span data-ttu-id="08edc-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="08edc-128">Unfocused</span></span>|<span data-ttu-id="08edc-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="08edc-129">FocusStates</span></span>|<span data-ttu-id="08edc-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="08edc-130">The control does not have focus.</span></span>|
|<span data-ttu-id="08edc-131">Valido</span><span class="sxs-lookup"><span data-stu-id="08edc-131">Valid</span></span>|<span data-ttu-id="08edc-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08edc-132">ValidationStates</span></span>|<span data-ttu-id="08edc-133">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="08edc-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="08edc-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="08edc-134">InvalidFocused</span></span>|<span data-ttu-id="08edc-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08edc-135">ValidationStates</span></span>|<span data-ttu-id="08edc-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="08edc-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="08edc-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="08edc-137">InvalidUnfocused</span></span>|<span data-ttu-id="08edc-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="08edc-138">ValidationStates</span></span>|<span data-ttu-id="08edc-139">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="08edc-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="08edc-140">Esempio di ControlTemplate RepeatButton</span><span class="sxs-lookup"><span data-stu-id="08edc-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="08edc-141">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.RepeatButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="08edc-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="08edc-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="08edc-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="08edc-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="08edc-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="08edc-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08edc-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="08edc-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="08edc-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="08edc-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="08edc-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="08edc-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="08edc-147">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="08edc-148">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="08edc-148">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
