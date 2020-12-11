---
title: Stili e modelli di ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: 1ece74e1c4aa1be9845bd812b29f2ad7f580d4e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966142"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="72830-102">Stili e modelli di ToolBar</span><span class="sxs-lookup"><span data-stu-id="72830-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="72830-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="72830-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="72830-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="72830-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="72830-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="72830-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="72830-106">Parti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="72830-106">ToolBar Parts</span></span>  
 <span data-ttu-id="72830-107">Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="72830-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="72830-108">Parte</span><span class="sxs-lookup"><span data-stu-id="72830-108">Part</span></span>|<span data-ttu-id="72830-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="72830-109">Type</span></span>|<span data-ttu-id="72830-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72830-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="72830-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="72830-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="72830-112">Oggetto che contiene i controlli in <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="72830-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="72830-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="72830-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="72830-114">Oggetto che contiene i controlli che si trovano nell'area di overflow dell'oggetto <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="72830-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="72830-115">Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.ToolBar> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> .</span><span class="sxs-lookup"><span data-stu-id="72830-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="72830-116">( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.ToolBar> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="72830-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="72830-117">Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="72830-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="72830-118">Stati della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="72830-118">ToolBar States</span></span>  
 <span data-ttu-id="72830-119">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="72830-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="72830-120">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="72830-120">VisualState Name</span></span>|<span data-ttu-id="72830-121">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="72830-121">VisualStateGroup Name</span></span>|<span data-ttu-id="72830-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72830-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="72830-123">Valido</span><span class="sxs-lookup"><span data-stu-id="72830-123">Valid</span></span>|<span data-ttu-id="72830-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72830-124">ValidationStates</span></span>|<span data-ttu-id="72830-125">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="72830-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="72830-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="72830-126">InvalidFocused</span></span>|<span data-ttu-id="72830-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72830-127">ValidationStates</span></span>|<span data-ttu-id="72830-128">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="72830-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="72830-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="72830-129">InvalidUnfocused</span></span>|<span data-ttu-id="72830-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72830-130">ValidationStates</span></span>|<span data-ttu-id="72830-131">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="72830-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="72830-132">Esempio di ControlTemplate della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="72830-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="72830-133">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="72830-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="72830-134">L'esempio precedente usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="72830-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="72830-135">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="72830-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72830-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72830-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="72830-137">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="72830-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="72830-138">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="72830-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="72830-139">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="72830-139">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="72830-140">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="72830-140">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
