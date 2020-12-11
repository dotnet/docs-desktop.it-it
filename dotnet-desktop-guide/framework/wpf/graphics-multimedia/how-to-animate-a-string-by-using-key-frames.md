---
title: 'Procedura: animare una stringa utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966121"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="6c6f0-102">Procedura: animare una stringa utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6c6f0-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="6c6f0-103">Questo esempio illustra come animare una stringa, che in questo esempio è la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="6c6f0-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c6f0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c6f0-104">Example</span></span>  
 <span data-ttu-id="6c6f0-105">Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un oggetto <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="6c6f0-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="6c6f0-106">Tutti i fotogrammi chiave in questo esempio usano un'istanza della <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione stringa creata con fotogrammi chiave può usare solo fotogrammi chiave discreti.</span><span class="sxs-lookup"><span data-stu-id="6c6f0-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="6c6f0-107">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creare salti improvvisi tra i valori, ovvero le modifiche apportate all'animazione si verificano rapidamente e non sono impercettibili.</span><span class="sxs-lookup"><span data-stu-id="6c6f0-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="6c6f0-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="6c6f0-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c6f0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c6f0-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="6c6f0-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6c6f0-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6c6f0-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="6c6f0-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
