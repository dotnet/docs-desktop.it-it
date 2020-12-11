---
title: Stili e modelli di DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 8a5d000dd67c1f5699c411db6ad1d7244ef0ad03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968533"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="73ad3-102">Stili e modelli di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="73ad3-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="73ad3-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="73ad3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="73ad3-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="73ad3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="73ad3-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="73ad3-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="73ad3-106">Parti di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="73ad3-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="73ad3-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="73ad3-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="73ad3-108">Parte</span><span class="sxs-lookup"><span data-stu-id="73ad3-108">Part</span></span>|<span data-ttu-id="73ad3-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="73ad3-109">Type</span></span>|<span data-ttu-id="73ad3-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73ad3-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="73ad3-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="73ad3-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="73ad3-112">Il contenuto e l'area di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="73ad3-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="73ad3-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="73ad3-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="73ad3-114">Casella di ricerca nella parte inferiore per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="73ad3-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="73ad3-115">Stati di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="73ad3-115">DocumentViewer States</span></span>  
 <span data-ttu-id="73ad3-116">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="73ad3-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="73ad3-117">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="73ad3-117">VisualState Name</span></span>|<span data-ttu-id="73ad3-118">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="73ad3-118">VisualStateGroup Name</span></span>|<span data-ttu-id="73ad3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73ad3-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="73ad3-120">Valido</span><span class="sxs-lookup"><span data-stu-id="73ad3-120">Valid</span></span>|<span data-ttu-id="73ad3-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73ad3-121">ValidationStates</span></span>|<span data-ttu-id="73ad3-122">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="73ad3-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="73ad3-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="73ad3-123">InvalidFocused</span></span>|<span data-ttu-id="73ad3-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73ad3-124">ValidationStates</span></span>|<span data-ttu-id="73ad3-125">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="73ad3-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="73ad3-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="73ad3-126">InvalidUnfocused</span></span>|<span data-ttu-id="73ad3-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="73ad3-127">ValidationStates</span></span>|<span data-ttu-id="73ad3-128">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="73ad3-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="73ad3-129">Esempio di ControlTemplate di DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="73ad3-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="73ad3-130">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DocumentViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="73ad3-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="73ad3-131">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="73ad3-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="73ad3-132">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="73ad3-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ad3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73ad3-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="73ad3-134">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="73ad3-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="73ad3-135">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="73ad3-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="73ad3-136">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="73ad3-136">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="73ad3-137">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="73ad3-137">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
