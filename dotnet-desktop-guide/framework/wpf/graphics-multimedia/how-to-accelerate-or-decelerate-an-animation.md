---
title: "Procedura: accelerare o decelerare un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966739"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="dfc04-102">Procedura: accelerare o decelerare un'animazione</span><span class="sxs-lookup"><span data-stu-id="dfc04-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="dfc04-103">Questo esempio illustra come rendere un'animazione accelerata e decelerata nel tempo.</span><span class="sxs-lookup"><span data-stu-id="dfc04-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="dfc04-104">Nell'esempio seguente, diversi rettangoli sono animati da animazioni con <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> Impostazioni e diverse <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> .</span><span class="sxs-lookup"><span data-stu-id="dfc04-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfc04-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfc04-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="dfc04-106">Il codice è stato omesso da questo esempio.</span><span class="sxs-lookup"><span data-stu-id="dfc04-106">Code has been omitted from this example.</span></span> <span data-ttu-id="dfc04-107">Per il codice completo, vedere il comportamento della [temporizzazione dell'animazione (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) o il [comportamento della temporizzazione dell'animazione (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="dfc04-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
