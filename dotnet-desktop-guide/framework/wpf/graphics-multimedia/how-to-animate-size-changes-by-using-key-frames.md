---
title: 'Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961108"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="7b3e9-102">Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7b3e9-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="7b3e9-103">Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="7b3e9-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b3e9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b3e9-104">Example</span></span>  
 <span data-ttu-id="7b3e9-105">Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un oggetto <xref:System.Windows.Media.ArcSegment> .</span><span class="sxs-lookup"><span data-stu-id="7b3e9-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="7b3e9-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7b3e9-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="7b3e9-107">Durante il primo mezzo secondo dell'animazione, usa un'istanza della <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe per aumentare gradualmente la dimensione dell'arco. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> creare una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="7b3e9-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="7b3e9-108">Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> classe per aumentare improvvisamente la dimensione dell'arco. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> creare salti improvvisi tra i valori, ovvero le modifiche delle dimensioni si verificano improvvisamente e non sono impercettibili.</span><span class="sxs-lookup"><span data-stu-id="7b3e9-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="7b3e9-109">Nei due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> classe per aumentare la dimensione dell'arco. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="7b3e9-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7b3e9-110">In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7b3e9-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7b3e9-111">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="7b3e9-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3e9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3e9-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="7b3e9-113">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7b3e9-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7b3e9-114">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7b3e9-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
