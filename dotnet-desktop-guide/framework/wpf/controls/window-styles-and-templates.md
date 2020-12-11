---
title: Stili e modelli di Window
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: ed488cf2fb5f4e73da544f8d758950fee318adf1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969277"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="1cb97-102">Stili e modelli di Window</span><span class="sxs-lookup"><span data-stu-id="1cb97-102">Window Styles and Templates</span></span>
<span data-ttu-id="1cb97-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="1cb97-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="1cb97-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="1cb97-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1cb97-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="1cb97-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="1cb97-106">Parti della finestra</span><span class="sxs-lookup"><span data-stu-id="1cb97-106">Window Parts</span></span>  
 <span data-ttu-id="1cb97-107">Il <xref:System.Windows.Window> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="1cb97-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="1cb97-108">Stati della finestra</span><span class="sxs-lookup"><span data-stu-id="1cb97-108">Window States</span></span>  
 <span data-ttu-id="1cb97-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="1cb97-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="1cb97-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="1cb97-110">VisualState Name</span></span>|<span data-ttu-id="1cb97-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1cb97-111">VisualStateGroup Name</span></span>|<span data-ttu-id="1cb97-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb97-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1cb97-113">Valido</span><span class="sxs-lookup"><span data-stu-id="1cb97-113">Valid</span></span>|<span data-ttu-id="1cb97-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1cb97-114">ValidationStates</span></span>|<span data-ttu-id="1cb97-115">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="1cb97-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1cb97-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1cb97-116">InvalidFocused</span></span>|<span data-ttu-id="1cb97-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1cb97-117">ValidationStates</span></span>|<span data-ttu-id="1cb97-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="1cb97-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1cb97-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1cb97-119">InvalidUnfocused</span></span>|<span data-ttu-id="1cb97-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1cb97-120">ValidationStates</span></span>|<span data-ttu-id="1cb97-121">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="1cb97-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="1cb97-122">Esempio di ControlTemplate finestra</span><span class="sxs-lookup"><span data-stu-id="1cb97-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="1cb97-123">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="1cb97-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="1cb97-124"><xref:System.Windows.Controls.ControlTemplate>Usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="1cb97-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1cb97-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1cb97-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb97-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cb97-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1cb97-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="1cb97-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1cb97-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="1cb97-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1cb97-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="1cb97-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="1cb97-130">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="1cb97-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
