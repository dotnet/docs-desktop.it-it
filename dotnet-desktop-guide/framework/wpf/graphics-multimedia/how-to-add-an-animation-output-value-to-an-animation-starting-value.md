---
title: "Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960862"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="744ac-102">Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione</span><span class="sxs-lookup"><span data-stu-id="744ac-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="744ac-103">Questo esempio illustra come aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="744ac-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="744ac-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="744ac-104">Example</span></span>  
 <span data-ttu-id="744ac-105">La <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà specifica se si desidera che il valore di output di un'animazione venga aggiunto al valore iniziale (valore di base) di una proprietà animata.</span><span class="sxs-lookup"><span data-stu-id="744ac-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="744ac-106">È possibile usare la <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà con la maggior parte delle animazioni di base e la maggior parte delle animazioni fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="744ac-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="744ac-107">Per altre informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="744ac-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="744ac-108">Nell'esempio seguente viene illustrato l'effetto dell'utilizzo della <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimation> e utilizzando la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> .</span><span class="sxs-lookup"><span data-stu-id="744ac-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="744ac-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="744ac-109">See also</span></span>

- [<span data-ttu-id="744ac-110">Accumulare valori di animazione durante i cicli ripetuti</span><span class="sxs-lookup"><span data-stu-id="744ac-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="744ac-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="744ac-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="744ac-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="744ac-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="744ac-113">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="744ac-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
