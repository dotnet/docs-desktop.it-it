---
title: Stili e modelli di ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: a33e99ed31b9154bcfacde988bc38c3852331722
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963688"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="8edf9-102">Stili e modelli di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="8edf9-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="8edf9-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="8edf9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="8edf9-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="8edf9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8edf9-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="8edf9-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="8edf9-106">Parti ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="8edf9-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="8edf9-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="8edf9-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="8edf9-108">Parte</span><span class="sxs-lookup"><span data-stu-id="8edf9-108">Part</span></span>|<span data-ttu-id="8edf9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8edf9-109">Type</span></span>|<span data-ttu-id="8edf9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8edf9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8edf9-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="8edf9-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="8edf9-112">Segnaposto per il contenuto in <xref:System.Windows.Controls.ScrollViewer> .</span><span class="sxs-lookup"><span data-stu-id="8edf9-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="8edf9-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="8edf9-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="8edf9-114">Oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> utilizzato per scorrere il contenuto orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="8edf9-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="8edf9-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="8edf9-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="8edf9-116">Oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> utilizzato per scorrere il contenuto verticalmente.</span><span class="sxs-lookup"><span data-stu-id="8edf9-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="8edf9-117">Stati di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="8edf9-117">ScrollViewer States</span></span>  
 <span data-ttu-id="8edf9-118">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="8edf9-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="8edf9-119">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="8edf9-119">VisualState Name</span></span>|<span data-ttu-id="8edf9-120">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8edf9-120">VisualStateGroup Name</span></span>|<span data-ttu-id="8edf9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8edf9-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8edf9-122">Valido</span><span class="sxs-lookup"><span data-stu-id="8edf9-122">Valid</span></span>|<span data-ttu-id="8edf9-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8edf9-123">ValidationStates</span></span>|<span data-ttu-id="8edf9-124">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="8edf9-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8edf9-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8edf9-125">InvalidFocused</span></span>|<span data-ttu-id="8edf9-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8edf9-126">ValidationStates</span></span>|<span data-ttu-id="8edf9-127">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="8edf9-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8edf9-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8edf9-128">InvalidUnfocused</span></span>|<span data-ttu-id="8edf9-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8edf9-129">ValidationStates</span></span>|<span data-ttu-id="8edf9-130">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="8edf9-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="8edf9-131">Esempio di ControlTemplate ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="8edf9-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="8edf9-132">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="8edf9-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="8edf9-133">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="8edf9-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8edf9-134">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8edf9-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edf9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8edf9-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8edf9-136">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="8edf9-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8edf9-137">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="8edf9-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8edf9-138">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8edf9-138">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="8edf9-139">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="8edf9-139">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
