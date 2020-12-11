---
title: Stili e modelli di GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 8648c284a1da3e7d629bec91210c8dd5ecdb8484
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966217"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="b5204-102">Stili e modelli di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5204-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="b5204-103">In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5204-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="b5204-104">È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="b5204-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b5204-105">Per altre informazioni, vedere [creare un modello per un controllo](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span><span class="sxs-lookup"><span data-stu-id="b5204-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="b5204-106">Parti GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5204-106">GroupBox Parts</span></span>  
 <span data-ttu-id="b5204-107">Il <xref:System.Windows.Controls.GroupBox> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="b5204-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="b5204-108">Stati di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5204-108">GroupBox States</span></span>  
 <span data-ttu-id="b5204-109">Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5204-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="b5204-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="b5204-110">VisualState Name</span></span>|<span data-ttu-id="b5204-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b5204-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b5204-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5204-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b5204-113">Valido</span><span class="sxs-lookup"><span data-stu-id="b5204-113">Valid</span></span>|<span data-ttu-id="b5204-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5204-114">ValidationStates</span></span>|<span data-ttu-id="b5204-115">Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .</span><span class="sxs-lookup"><span data-stu-id="b5204-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b5204-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b5204-116">InvalidFocused</span></span>|<span data-ttu-id="b5204-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5204-117">ValidationStates</span></span>|<span data-ttu-id="b5204-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="b5204-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b5204-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b5204-119">InvalidUnfocused</span></span>|<span data-ttu-id="b5204-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b5204-120">ValidationStates</span></span>|<span data-ttu-id="b5204-121">Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .</span><span class="sxs-lookup"><span data-stu-id="b5204-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="b5204-122">Esempio di ControlTemplate di GroupBox</span><span class="sxs-lookup"><span data-stu-id="b5204-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="b5204-123">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="b5204-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="b5204-124"><xref:System.Windows.Controls.ControlTemplate>Usa una o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="b5204-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b5204-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b5204-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5204-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5204-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b5204-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="b5204-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b5204-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="b5204-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b5204-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="b5204-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="b5204-130">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="b5204-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
