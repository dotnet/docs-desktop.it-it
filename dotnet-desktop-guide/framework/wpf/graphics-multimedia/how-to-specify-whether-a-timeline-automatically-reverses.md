---
title: 'Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961273"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="cbef9-102">Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno</span><span class="sxs-lookup"><span data-stu-id="cbef9-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="cbef9-103">La proprietà di una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> determina se viene riprodotta in senso inverso dopo il completamento di un'iterazione in attesa.</span><span class="sxs-lookup"><span data-stu-id="cbef9-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="cbef9-104">Nell'esempio seguente vengono illustrate diverse animazioni con valori di durata e destinazione identici, ma con <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="cbef9-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="cbef9-105">Per illustrare il comportamento della <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà con impostazioni diverse <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni sono impostate per la ripetizione.</span><span class="sxs-lookup"><span data-stu-id="cbef9-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="cbef9-106">Nell'ultima animazione viene illustrato il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> funzionamento della proprietà sulle sequenze temporali nidificate.</span><span class="sxs-lookup"><span data-stu-id="cbef9-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbef9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbef9-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
