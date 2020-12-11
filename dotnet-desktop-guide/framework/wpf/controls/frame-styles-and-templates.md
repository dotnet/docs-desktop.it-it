---
title: Stili e modelli di Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 106a7a2a0138250261ce31b0cbd98173b14e749a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952320"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="1f84a-102">Stili e modelli di Frame</span><span class="sxs-lookup"><span data-stu-id="1f84a-102">Frame Styles and Templates</span></span>
<span data-ttu-id="1f84a-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="1f84a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="1f84a-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="1f84a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1f84a-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="1f84a-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="1f84a-106">Parti cornice</span><span class="sxs-lookup"><span data-stu-id="1f84a-106">Frame Parts</span></span>  
 <span data-ttu-id="1f84a-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="1f84a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1f84a-108">Parte</span><span class="sxs-lookup"><span data-stu-id="1f84a-108">Part</span></span>|<span data-ttu-id="1f84a-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="1f84a-109">Type</span></span>|<span data-ttu-id="1f84a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f84a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1f84a-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="1f84a-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="1f84a-112">Area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="1f84a-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="1f84a-113">Stati frame</span><span class="sxs-lookup"><span data-stu-id="1f84a-113">Frame States</span></span>  
 <span data-ttu-id="1f84a-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="1f84a-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1f84a-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="1f84a-115">VisualState Name</span></span>|<span data-ttu-id="1f84a-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1f84a-116">VisualStateGroup Name</span></span>|<span data-ttu-id="1f84a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f84a-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1f84a-118">Valido</span><span class="sxs-lookup"><span data-stu-id="1f84a-118">Valid</span></span>|<span data-ttu-id="1f84a-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f84a-119">ValidationStates</span></span>|<span data-ttu-id="1f84a-120">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="1f84a-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1f84a-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1f84a-121">InvalidFocused</span></span>|<span data-ttu-id="1f84a-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f84a-122">ValidationStates</span></span>|<span data-ttu-id="1f84a-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="1f84a-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1f84a-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1f84a-124">InvalidUnfocused</span></span>|<span data-ttu-id="1f84a-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f84a-125">ValidationStates</span></span>|<span data-ttu-id="1f84a-126">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="1f84a-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="1f84a-127">Esempio di ControlTemplate frame</span><span class="sxs-lookup"><span data-stu-id="1f84a-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="1f84a-128">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Frame> controllo.</span><span class="sxs-lookup"><span data-stu-id="1f84a-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="1f84a-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="1f84a-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1f84a-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1f84a-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f84a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f84a-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1f84a-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="1f84a-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1f84a-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="1f84a-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1f84a-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="1f84a-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="1f84a-135">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="1f84a-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
