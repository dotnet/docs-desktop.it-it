---
title: 'Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965491"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="54d7a-102">Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività</span><span class="sxs-lookup"><span data-stu-id="54d7a-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="54d7a-103">In questo esempio viene illustrato come specificare <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="54d7a-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54d7a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="54d7a-104">Example</span></span>  
 <span data-ttu-id="54d7a-105">La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un oggetto <xref:System.Windows.Media.Animation.Timeline> determina cosa accade al valore di una proprietà animata quando non viene animata, ovvero quando <xref:System.Windows.Media.Animation.Timeline> è inattivo, ma il padre <xref:System.Windows.Media.Animation.Timeline> è all'interno del periodo attivo o di attesa.</span><span class="sxs-lookup"><span data-stu-id="54d7a-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="54d7a-106">Ad esempio, una proprietà animata rimane in corrispondenza del valore finale dopo che l'animazione termina o Ripristina il valore che aveva prima dell'avvio dell'animazione?</span><span class="sxs-lookup"><span data-stu-id="54d7a-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="54d7a-107">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare l'oggetto <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="54d7a-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="54d7a-108">Ogni rettangolo utilizza un <xref:System.Windows.Media.Animation.Timeline> oggetto diverso.</span><span class="sxs-lookup"><span data-stu-id="54d7a-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="54d7a-109">Uno <xref:System.Windows.Media.Animation.Timeline> ha un oggetto <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop> , che fa sì che la larghezza del rettangolo torni al valore non animato al termine dell'operazione <xref:System.Windows.Media.Animation.Timeline> .</span><span class="sxs-lookup"><span data-stu-id="54d7a-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="54d7a-110">L'altro <xref:System.Windows.Media.Animation.Timeline> ha <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> , che fa sì che la larghezza rimanga al suo valore finale al termine dell'operazione <xref:System.Windows.Media.Animation.Timeline> .</span><span class="sxs-lookup"><span data-stu-id="54d7a-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="54d7a-111">Per l'esempio completo, vedere [raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="54d7a-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d7a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54d7a-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="54d7a-113">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="54d7a-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="54d7a-114">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="54d7a-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
