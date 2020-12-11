---
title: Stili e modelli di ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 781c185e01621767a82ebee054c578ed291c9b79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966151"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="f05f9-102">Stili e modelli di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f05f9-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="f05f9-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="f05f9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="f05f9-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="f05f9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f05f9-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="f05f9-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="f05f9-106">Parti ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f05f9-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="f05f9-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="f05f9-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f05f9-108">Parte</span><span class="sxs-lookup"><span data-stu-id="f05f9-108">Part</span></span>|<span data-ttu-id="f05f9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="f05f9-109">Type</span></span>|<span data-ttu-id="f05f9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f05f9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f05f9-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="f05f9-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f05f9-112">Oggetto che indica lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="f05f9-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="f05f9-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="f05f9-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f05f9-114">Oggetto che definisce il percorso dell'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="f05f9-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="f05f9-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="f05f9-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f05f9-116">Oggetto che abbellisce l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="f05f9-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="f05f9-117">Stati ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f05f9-117">ProgressBar States</span></span>  
 <span data-ttu-id="f05f9-118">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="f05f9-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f05f9-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="f05f9-119">VisualState Name</span></span>|<span data-ttu-id="f05f9-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f05f9-120">VisualStateGroup Name</span></span>|<span data-ttu-id="f05f9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f05f9-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f05f9-122">Determinato</span><span class="sxs-lookup"><span data-stu-id="f05f9-122">Determinate</span></span>|<span data-ttu-id="f05f9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f05f9-123">CommonStates</span></span>|<span data-ttu-id="f05f9-124"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento in base alla <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f05f9-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="f05f9-125">Indeterminato</span><span class="sxs-lookup"><span data-stu-id="f05f9-125">Indeterminate</span></span>|<span data-ttu-id="f05f9-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f05f9-126">CommonStates</span></span>|<span data-ttu-id="f05f9-127"><xref:System.Windows.Controls.ProgressBar> segnala lo stato di avanzamento generico con un modello ripetuto.</span><span class="sxs-lookup"><span data-stu-id="f05f9-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="f05f9-128">Valido</span><span class="sxs-lookup"><span data-stu-id="f05f9-128">Valid</span></span>|<span data-ttu-id="f05f9-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f05f9-129">ValidationStates</span></span>|<span data-ttu-id="f05f9-130">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="f05f9-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f05f9-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f05f9-131">InvalidFocused</span></span>|<span data-ttu-id="f05f9-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f05f9-132">ValidationStates</span></span>|<span data-ttu-id="f05f9-133">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="f05f9-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f05f9-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f05f9-134">InvalidUnfocused</span></span>|<span data-ttu-id="f05f9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f05f9-135">ValidationStates</span></span>|<span data-ttu-id="f05f9-136">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="f05f9-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="f05f9-137">Esempio di ControlTemplate di ProgressBar</span><span class="sxs-lookup"><span data-stu-id="f05f9-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="f05f9-138">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ProgressBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="f05f9-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="f05f9-139">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="f05f9-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f05f9-140">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f05f9-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05f9-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f05f9-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f05f9-142">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="f05f9-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f05f9-143">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="f05f9-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f05f9-144">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="f05f9-144">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="f05f9-145">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="f05f9-145">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
