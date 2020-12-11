---
title: Stili e modelli di ContextMenu
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 0f168c440c804c543ee9923d0021677ac529d5e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967093"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="3b149-102">Stili e modelli di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b149-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="3b149-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="3b149-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="3b149-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="3b149-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3b149-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="3b149-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="3b149-106">Parti ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b149-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="3b149-107">Il <xref:System.Windows.Controls.ContextMenu> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="3b149-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="3b149-108">Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.ContextMenu> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> .</span><span class="sxs-lookup"><span data-stu-id="3b149-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="3b149-109">( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.ContextMenu> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).</span><span class="sxs-lookup"><span data-stu-id="3b149-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="3b149-110">Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="3b149-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="3b149-111">Stati ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b149-111">ContextMenu States</span></span>  
 <span data-ttu-id="3b149-112">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="3b149-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="3b149-113">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="3b149-113">VisualState Name</span></span>|<span data-ttu-id="3b149-114">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3b149-114">VisualStateGroup Name</span></span>|<span data-ttu-id="3b149-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b149-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3b149-116">Valido</span><span class="sxs-lookup"><span data-stu-id="3b149-116">Valid</span></span>|<span data-ttu-id="3b149-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b149-117">ValidationStates</span></span>|<span data-ttu-id="3b149-118">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="3b149-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3b149-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3b149-119">InvalidFocused</span></span>|<span data-ttu-id="3b149-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b149-120">ValidationStates</span></span>|<span data-ttu-id="3b149-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="3b149-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3b149-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3b149-122">InvalidUnfocused</span></span>|<span data-ttu-id="3b149-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b149-123">ValidationStates</span></span>|<span data-ttu-id="3b149-124">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="3b149-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="3b149-125">Esempio di ControlTemplate ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b149-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="3b149-126">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ContextMenu> controllo.</span><span class="sxs-lookup"><span data-stu-id="3b149-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="3b149-127"><xref:System.Windows.Controls.ControlTemplate>Utilizza le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="3b149-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3b149-128">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3b149-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b149-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b149-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3b149-130">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="3b149-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3b149-131">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="3b149-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3b149-132">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="3b149-132">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="3b149-133">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="3b149-133">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
