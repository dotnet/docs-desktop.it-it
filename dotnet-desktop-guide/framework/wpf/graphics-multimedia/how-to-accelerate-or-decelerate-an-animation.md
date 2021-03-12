---
title: "Procedura: accelerare o decelerare un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 04912e4bd51aba5ddcea7bb5f5a91bbb6501b6c3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604290"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="3e408-102">Procedura: accelerare o decelerare un'animazione</span><span class="sxs-lookup"><span data-stu-id="3e408-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="3e408-103">Questo esempio illustra come rendere un'animazione accelerata e decelerata nel tempo.</span><span class="sxs-lookup"><span data-stu-id="3e408-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="3e408-104">Nell'esempio seguente, diversi rettangoli sono animati da animazioni con <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> Impostazioni e diverse <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> .</span><span class="sxs-lookup"><span data-stu-id="3e408-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e408-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e408-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="3e408-106">Il codice è stato omesso da questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3e408-106">Code has been omitted from this example.</span></span> <span data-ttu-id="3e408-107">Per il codice completo, vedere il comportamento della [temporizzazione dell'animazione (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) o il [comportamento della temporizzazione dell'animazione (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="3e408-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
