---
title: 'Procedura: animare un valore BorderThickness'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969532"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="27989-102">Procedura: animare un valore BorderThickness</span><span class="sxs-lookup"><span data-stu-id="27989-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="27989-103">Questo esempio illustra come animare le modifiche allo spessore di un bordo usando la <xref:System.Windows.Media.Animation.ThicknessAnimation> classe.</span><span class="sxs-lookup"><span data-stu-id="27989-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27989-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="27989-104">Example</span></span>  
 <span data-ttu-id="27989-105">Nell'esempio seguente viene animato lo spessore di un bordo usando <xref:System.Windows.Media.Animation.ThicknessAnimation> .</span><span class="sxs-lookup"><span data-stu-id="27989-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="27989-106">Nell'esempio viene utilizzata la <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà di <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="27989-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="27989-107">Per l'esempio completo, vedere [raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="27989-107">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27989-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27989-108">See also</span></span>

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="27989-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="27989-109">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="27989-110">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="27989-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="27989-111">Aggiungere un'animazione allo spessore di un bordo usando i fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="27989-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
