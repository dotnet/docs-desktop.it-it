---
title: Stili e modelli di TextBox
description: Informazioni sugli stili e i modelli per il controllo TextBox Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: e8c1bcbdeaf8b9b6d8bba2ccaf802e48dca02047
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951702"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="75f78-104">Stili e modelli di TextBox</span><span class="sxs-lookup"><span data-stu-id="75f78-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="75f78-105">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="75f78-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="75f78-106">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="75f78-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="75f78-107">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="75f78-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="75f78-108">Parti casella di testo</span><span class="sxs-lookup"><span data-stu-id="75f78-108">TextBox Parts</span></span>  
 <span data-ttu-id="75f78-109">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="75f78-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="75f78-110">Parte</span><span class="sxs-lookup"><span data-stu-id="75f78-110">Part</span></span>|<span data-ttu-id="75f78-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="75f78-111">Type</span></span>|<span data-ttu-id="75f78-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f78-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="75f78-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="75f78-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="75f78-114">Elemento visivo che può contenere un oggetto <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="75f78-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="75f78-115">Il testo di <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="75f78-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="75f78-116">Stati TextBox</span><span class="sxs-lookup"><span data-stu-id="75f78-116">TextBox States</span></span>  
 <span data-ttu-id="75f78-117">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="75f78-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="75f78-118">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="75f78-118">VisualState Name</span></span>|<span data-ttu-id="75f78-119">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="75f78-119">VisualStateGroup Name</span></span>|<span data-ttu-id="75f78-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f78-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="75f78-121">Normale</span><span class="sxs-lookup"><span data-stu-id="75f78-121">Normal</span></span>|<span data-ttu-id="75f78-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75f78-122">CommonStates</span></span>|<span data-ttu-id="75f78-123">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="75f78-123">The default state.</span></span>|  
|<span data-ttu-id="75f78-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="75f78-124">MouseOver</span></span>|<span data-ttu-id="75f78-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75f78-125">CommonStates</span></span>|<span data-ttu-id="75f78-126">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="75f78-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="75f78-127">Disabled</span><span class="sxs-lookup"><span data-stu-id="75f78-127">Disabled</span></span>|<span data-ttu-id="75f78-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75f78-128">CommonStates</span></span>|<span data-ttu-id="75f78-129">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="75f78-129">The control is disabled.</span></span>|  
|<span data-ttu-id="75f78-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="75f78-130">ReadOnly</span></span>|<span data-ttu-id="75f78-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75f78-131">CommonStates</span></span>|<span data-ttu-id="75f78-132">L'utente non può modificare il testo in <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="75f78-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="75f78-133">Con stato attivo</span><span class="sxs-lookup"><span data-stu-id="75f78-133">Focused</span></span>|<span data-ttu-id="75f78-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="75f78-134">FocusStates</span></span>|<span data-ttu-id="75f78-135">Il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="75f78-135">The control has focus.</span></span>|  
|<span data-ttu-id="75f78-136">Con stato non attivo</span><span class="sxs-lookup"><span data-stu-id="75f78-136">Unfocused</span></span>|<span data-ttu-id="75f78-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="75f78-137">FocusStates</span></span>|<span data-ttu-id="75f78-138">Il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="75f78-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="75f78-139">Valido</span><span class="sxs-lookup"><span data-stu-id="75f78-139">Valid</span></span>|<span data-ttu-id="75f78-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75f78-140">ValidationStates</span></span>|<span data-ttu-id="75f78-141">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="75f78-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="75f78-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="75f78-142">InvalidFocused</span></span>|<span data-ttu-id="75f78-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75f78-143">ValidationStates</span></span>|<span data-ttu-id="75f78-144">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="75f78-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="75f78-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="75f78-145">InvalidUnfocused</span></span>|<span data-ttu-id="75f78-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75f78-146">ValidationStates</span></span>|<span data-ttu-id="75f78-147">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="75f78-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="75f78-148">Esempio di ControlTemplate TextBox</span><span class="sxs-lookup"><span data-stu-id="75f78-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="75f78-149">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="75f78-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="75f78-150">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="75f78-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="75f78-151">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="75f78-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f78-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f78-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="75f78-153">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="75f78-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="75f78-154">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="75f78-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="75f78-155">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="75f78-155">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="75f78-156">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="75f78-156">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
