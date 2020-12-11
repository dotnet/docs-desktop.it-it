---
title: 'Procedura: animare lo spessore di un bordo utilizzando frame chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960841"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="f2ca3-102">Procedura: animare lo spessore di un bordo utilizzando frame chiave</span><span class="sxs-lookup"><span data-stu-id="f2ca3-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="f2ca3-103">Questo esempio illustra come animare la <xref:System.Windows.Controls.Control.BorderThickness%2A> proprietà di un oggetto <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="f2ca3-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2ca3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2ca3-104">Example</span></span>  
 <span data-ttu-id="f2ca3-105">Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Controls.Control.BorderThickness%2A> proprietà di un oggetto <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="f2ca3-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="f2ca3-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f2ca3-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="f2ca3-107">Durante il primo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> classe per aumentare gradualmente lo spessore del bordo.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="f2ca3-108">Nell'esempio viene usato <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> per creare un aumento lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="f2ca3-109">Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> classe per aumentare improvvisamente lo spessore del bordo.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="f2ca3-110">I fotogrammi chiave discreti come quelli derivati da <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> creano salti improvvisi tra valori, ovvero lo spostamento dell'animazione è di tipo Jerky.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="f2ca3-111">Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> classe per ridurre lo spessore del bordo.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="f2ca3-112">I fotogrammi chiave spline come quelli derivati da <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> creano una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="f2ca3-113">In questo fotogramma chiave l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="f2ca3-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f2ca3-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="f2ca3-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ca3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ca3-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="f2ca3-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="f2ca3-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f2ca3-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="f2ca3-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="f2ca3-118">Animare un valore BorderThickness</span><span class="sxs-lookup"><span data-stu-id="f2ca3-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
