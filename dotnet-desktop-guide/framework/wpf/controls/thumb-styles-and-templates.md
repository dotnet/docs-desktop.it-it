---
title: Stili e modelli di Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 6c14280f9514e3c9b1716b55410a46cf843f6b8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951732"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="5f4c1-102">Stili e modelli di Thumb</span><span class="sxs-lookup"><span data-stu-id="5f4c1-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="5f4c1-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="5f4c1-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5f4c1-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="5f4c1-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="5f4c1-106">Parti Thumb</span><span class="sxs-lookup"><span data-stu-id="5f4c1-106">Thumb Parts</span></span>

<span data-ttu-id="5f4c1-107">Il <xref:System.Windows.Controls.Primitives.Thumb> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="5f4c1-108">Stati Thumb</span><span class="sxs-lookup"><span data-stu-id="5f4c1-108">Thumb States</span></span>

<span data-ttu-id="5f4c1-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="5f4c1-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="5f4c1-110">VisualState Name</span></span>|<span data-ttu-id="5f4c1-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5f4c1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5f4c1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f4c1-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="5f4c1-113">Normale</span><span class="sxs-lookup"><span data-stu-id="5f4c1-113">Normal</span></span>|<span data-ttu-id="5f4c1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-114">CommonStates</span></span>|<span data-ttu-id="5f4c1-115">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-115">The default state.</span></span>|
|<span data-ttu-id="5f4c1-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5f4c1-116">MouseOver</span></span>|<span data-ttu-id="5f4c1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-117">CommonStates</span></span>|<span data-ttu-id="5f4c1-118">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="5f4c1-119">Premuto</span><span class="sxs-lookup"><span data-stu-id="5f4c1-119">Pressed</span></span>|<span data-ttu-id="5f4c1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-120">CommonStates</span></span>|<span data-ttu-id="5f4c1-121">Il controllo è premuto.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-121">The control is pressed.</span></span>|
|<span data-ttu-id="5f4c1-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="5f4c1-122">Disabled</span></span>|<span data-ttu-id="5f4c1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-123">CommonStates</span></span>|<span data-ttu-id="5f4c1-124">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-124">The control is disabled.</span></span>|
|<span data-ttu-id="5f4c1-125">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="5f4c1-125">Focused</span></span>|<span data-ttu-id="5f4c1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-126">FocusStates</span></span>|<span data-ttu-id="5f4c1-127">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-127">The control has focus.</span></span>|
|<span data-ttu-id="5f4c1-128">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="5f4c1-128">Unfocused</span></span>|<span data-ttu-id="5f4c1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-129">FocusStates</span></span>|<span data-ttu-id="5f4c1-130">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-130">The control does not have focus.</span></span>|
|<span data-ttu-id="5f4c1-131">Valido</span><span class="sxs-lookup"><span data-stu-id="5f4c1-131">Valid</span></span>|<span data-ttu-id="5f4c1-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-132">ValidationStates</span></span>|<span data-ttu-id="5f4c1-133">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="5f4c1-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="5f4c1-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5f4c1-134">InvalidFocused</span></span>|<span data-ttu-id="5f4c1-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-135">ValidationStates</span></span>|<span data-ttu-id="5f4c1-136">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="5f4c1-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="5f4c1-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5f4c1-137">InvalidUnfocused</span></span>|<span data-ttu-id="5f4c1-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f4c1-138">ValidationStates</span></span>|<span data-ttu-id="5f4c1-139">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="5f4c1-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="5f4c1-140">Esempio di ControlTemplate Thumb</span><span class="sxs-lookup"><span data-stu-id="5f4c1-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="5f4c1-141">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="5f4c1-142">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="5f4c1-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="5f4c1-143">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5f4c1-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f4c1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f4c1-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5f4c1-145">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="5f4c1-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5f4c1-146">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="5f4c1-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5f4c1-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="5f4c1-147">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="5f4c1-148">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="5f4c1-148">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
