---
title: "Procedura: attivare un'animazione quando il valore di una proprietà viene modificato"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967972"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="b089e-102">Procedura: attivare un'animazione quando il valore di una proprietà viene modificato</span><span class="sxs-lookup"><span data-stu-id="b089e-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="b089e-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Trigger> per avviare un oggetto <xref:System.Windows.Media.Animation.Storyboard> quando viene modificato il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b089e-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="b089e-104">È possibile usare un oggetto <xref:System.Windows.Trigger> all'interno di un oggetto <xref:System.Windows.Style> , <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate> .</span><span class="sxs-lookup"><span data-stu-id="b089e-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b089e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b089e-105">Example</span></span>  
 <span data-ttu-id="b089e-106">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Trigger> per animare l'oggetto <xref:System.Windows.UIElement.Opacity%2A> di un oggetto <xref:System.Windows.Controls.Button> quando la relativa <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà diventa `true` .</span><span class="sxs-lookup"><span data-stu-id="b089e-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="b089e-107">Le animazioni applicate dagli <xref:System.Windows.Trigger> oggetti proprietà si comportano in modo più complesso rispetto alle animazioni <xref:System.Windows.EventTrigger> o alle animazioni avviate mediante i <xref:System.Windows.Media.Animation.Storyboard> metodi.</span><span class="sxs-lookup"><span data-stu-id="b089e-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="b089e-108">Le "consegne" con animazioni definite da altri <xref:System.Windows.Trigger> oggetti, ma compongono con <xref:System.Windows.EventTrigger> animazioni attivate dal metodo.</span><span class="sxs-lookup"><span data-stu-id="b089e-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b089e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b089e-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="b089e-110">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b089e-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="b089e-111">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="b089e-111">Storyboards Overview</span></span>](storyboards-overview.md)
