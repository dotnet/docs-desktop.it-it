---
title: 'Procedura: applicare un oggetto FocusVisualStyle a un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: c27994bfbc77f7cbe360ad3aab94827900e52232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964075"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="43674-102">Procedura: applicare un oggetto FocusVisualStyle a un controllo</span><span class="sxs-lookup"><span data-stu-id="43674-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="43674-103">Questo esempio illustra come creare uno stile di visualizzazione dello stato attivo nelle risorse e applicare lo stile a un controllo usando la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="43674-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43674-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="43674-104">Example</span></span>  
 <span data-ttu-id="43674-105">Nell'esempio seguente viene definito uno stile che crea la composizione di controlli aggiuntivi che si applica solo quando il controllo è attivo nella tastiera [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43674-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="43674-106">Questa operazione viene eseguita definendo uno stile con un oggetto <xref:System.Windows.Controls.ControlTemplate> , quindi facendo riferimento a tale stile come risorsa quando si imposta la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="43674-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="43674-107">Un rettangolo esterno simile a un bordo viene inserito all'esterno dell'area rettangolare.</span><span class="sxs-lookup"><span data-stu-id="43674-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="43674-108">Se non diversamente modificato, il dimensionamento dello stile USA <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="43674-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="43674-109">In questo esempio vengono impostati i valori negativi per l'oggetto <xref:System.Windows.FrameworkElement.Margin%2A> affinché il bordo appaia leggermente all'esterno del controllo attivo.</span><span class="sxs-lookup"><span data-stu-id="43674-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="43674-110">Un oggetto <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o da uno stile del tema; lo stile principale di un controllo può comunque essere creato utilizzando un oggetto <xref:System.Windows.Controls.ControlTemplate> e impostando tale stile sulla <xref:System.Windows.FrameworkElement.Style%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="43674-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="43674-111">Gli stili di visualizzazione dello stato attivo devono essere usati in modo coerente in un tema o in un'interfaccia utente, anziché usare uno diverso per ogni elemento attivabile.</span><span class="sxs-lookup"><span data-stu-id="43674-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="43674-112">Per informazioni dettagliate, vedere applicazione di [stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="43674-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43674-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43674-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="43674-114">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="43674-114">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="43674-115">Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="43674-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
