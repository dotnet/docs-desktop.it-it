---
title: Stili e modelli di ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 4c4a0e4eeb6d9d58470973dc8ae1877b8fef9bde
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966307"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="4af09-102">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4af09-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="4af09-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="4af09-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="4af09-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="4af09-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4af09-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="4af09-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="4af09-106">Parti della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="4af09-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="4af09-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="4af09-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4af09-108">Parte</span><span class="sxs-lookup"><span data-stu-id="4af09-108">Part</span></span>|<span data-ttu-id="4af09-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="4af09-109">Type</span></span>|<span data-ttu-id="4af09-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4af09-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4af09-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="4af09-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="4af09-112">Contenitore per l'elemento che indica la posizione dell'oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> .</span><span class="sxs-lookup"><span data-stu-id="4af09-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="4af09-113">Stati ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4af09-113">ScrollBar States</span></span>  
 <span data-ttu-id="4af09-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="4af09-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4af09-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="4af09-115">VisualState Name</span></span>|<span data-ttu-id="4af09-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4af09-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4af09-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4af09-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4af09-118">Normale</span><span class="sxs-lookup"><span data-stu-id="4af09-118">Normal</span></span>|<span data-ttu-id="4af09-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4af09-119">CommonStates</span></span>|<span data-ttu-id="4af09-120">Lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="4af09-120">The default state.</span></span>|  
|<span data-ttu-id="4af09-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4af09-121">MouseOver</span></span>|<span data-ttu-id="4af09-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4af09-122">CommonStates</span></span>|<span data-ttu-id="4af09-123">Il puntatore del mouse è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="4af09-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4af09-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="4af09-124">Disabled</span></span>|<span data-ttu-id="4af09-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4af09-125">CommonStates</span></span>|<span data-ttu-id="4af09-126">Il controllo è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4af09-126">The control is disabled.</span></span>|  
|<span data-ttu-id="4af09-127">Valido</span><span class="sxs-lookup"><span data-stu-id="4af09-127">Valid</span></span>|<span data-ttu-id="4af09-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4af09-128">ValidationStates</span></span>|<span data-ttu-id="4af09-129">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="4af09-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4af09-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4af09-130">InvalidFocused</span></span>|<span data-ttu-id="4af09-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4af09-131">ValidationStates</span></span>|<span data-ttu-id="4af09-132">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="4af09-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="4af09-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4af09-133">InvalidUnfocused</span></span>|<span data-ttu-id="4af09-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4af09-134">ValidationStates</span></span>|<span data-ttu-id="4af09-135">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="4af09-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="4af09-136">Esempio di ControlTemplate ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4af09-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="4af09-137">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.ScrollBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="4af09-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="4af09-138">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="4af09-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4af09-139">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4af09-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af09-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af09-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4af09-141">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="4af09-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4af09-142">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="4af09-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4af09-143">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="4af09-143">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="4af09-144">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="4af09-144">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
