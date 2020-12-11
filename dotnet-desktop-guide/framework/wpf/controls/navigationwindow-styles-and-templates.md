---
title: Stili e modelli di NavigationWindow
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 1189a6709a77af0a777b908f6aacab90288d01e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968590"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="8480f-102">Stili e modelli di NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="8480f-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="8480f-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="8480f-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="8480f-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="8480f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8480f-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="8480f-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="8480f-106">Parti NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="8480f-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="8480f-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="8480f-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="8480f-108">Parte</span><span class="sxs-lookup"><span data-stu-id="8480f-108">Part</span></span>|<span data-ttu-id="8480f-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8480f-109">Type</span></span>|<span data-ttu-id="8480f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8480f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8480f-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="8480f-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="8480f-112">Area del contenuto.</span><span class="sxs-lookup"><span data-stu-id="8480f-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="8480f-113">Stati NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="8480f-113">NavigationWindow States</span></span>  
 <span data-ttu-id="8480f-114">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Navigation.NavigationWindow> controllo.</span><span class="sxs-lookup"><span data-stu-id="8480f-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="8480f-115">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="8480f-115">VisualState Name</span></span>|<span data-ttu-id="8480f-116">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8480f-116">VisualStateGroup Name</span></span>|<span data-ttu-id="8480f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8480f-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8480f-118">Valido</span><span class="sxs-lookup"><span data-stu-id="8480f-118">Valid</span></span>|<span data-ttu-id="8480f-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8480f-119">ValidationStates</span></span>|<span data-ttu-id="8480f-120">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="8480f-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8480f-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8480f-121">InvalidFocused</span></span>|<span data-ttu-id="8480f-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8480f-122">ValidationStates</span></span>|<span data-ttu-id="8480f-123">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="8480f-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8480f-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8480f-124">InvalidUnfocused</span></span>|<span data-ttu-id="8480f-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8480f-125">ValidationStates</span></span>|<span data-ttu-id="8480f-126">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="8480f-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="8480f-127">Esempio di ControlTemplate NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="8480f-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="8480f-128">Sebbene in questo esempio siano contenuti tutti gli elementi definiti in <xref:System.Windows.Controls.ControlTemplate> di un oggetto <xref:System.Windows.Navigation.NavigationWindow> per impostazione predefinita, i valori specifici devono essere considerati come esempi.</span><span class="sxs-lookup"><span data-stu-id="8480f-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="8480f-129">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="8480f-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8480f-130">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8480f-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8480f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8480f-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8480f-132">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="8480f-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8480f-133">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="8480f-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8480f-134">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8480f-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="8480f-135">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="8480f-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
