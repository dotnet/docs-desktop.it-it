---
title: 'Procedura: animare una proprietà utilizzando un oggetto AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952302"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="08077-102">Procedura: animare una proprietà utilizzando un oggetto AnimationClock</span><span class="sxs-lookup"><span data-stu-id="08077-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="08077-103">Questo esempio illustra come usare <xref:System.Windows.Media.Animation.Clock> gli oggetti per animare una proprietà.</span><span class="sxs-lookup"><span data-stu-id="08077-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="08077-104">Esistono tre modi per animare una proprietà di dipendenza:</span><span class="sxs-lookup"><span data-stu-id="08077-104">There are three ways to animate a dependency property:</span></span>  
  
- <span data-ttu-id="08077-105">Creare un oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> e associarlo a tale proprietà utilizzando un oggetto <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="08077-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
- <span data-ttu-id="08077-106">Usare il metodo dell'oggetto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> per applicare un singolo oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> a una proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="08077-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
- <span data-ttu-id="08077-107">Creare un oggetto <xref:System.Windows.Media.Animation.AnimationClock> da un oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> e applicarlo a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="08077-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="08077-108"><xref:System.Windows.Media.Animation.Storyboard> gli oggetti e il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo consentono di animare le proprietà senza creare e distribuire direttamente orologi (per alcuni esempi, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md) e [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); gli orologi vengono creati e distribuiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="08077-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08077-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="08077-109">Example</span></span>  
 <span data-ttu-id="08077-110">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.</span><span class="sxs-lookup"><span data-stu-id="08077-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="08077-111">Per un esempio che illustra come controllare in modo interattivo un oggetto <xref:System.Windows.Media.Animation.Clock> dopo l'avvio, vedere controllare in modo [interattivo un orologio](how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="08077-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08077-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08077-112">See also</span></span>

- [<span data-ttu-id="08077-113">Aggiungere un'animazione a una proprietà usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="08077-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="08077-114">Aggiungere un'animazione a una proprietà senza usare uno storyboard</span><span class="sxs-lookup"><span data-stu-id="08077-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="08077-115">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="08077-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
