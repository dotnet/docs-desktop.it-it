---
title: 'Procedura: animare un rettangolo utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952301"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="24759-102">Procedura: animare un rettangolo utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="24759-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="24759-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un oggetto utilizzando <xref:System.Windows.Media.RectangleGeometry> fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="24759-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24759-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="24759-104">Example</span></span>  
 <span data-ttu-id="24759-105">Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un oggetto <xref:System.Windows.Media.RectangleGeometry> .</span><span class="sxs-lookup"><span data-stu-id="24759-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="24759-106">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="24759-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="24759-107">Durante i primi due secondi, usa un'istanza della <xref:System.Windows.Media.Animation.LinearRectKeyFrame> classe per aggiungere un'animazione a una modifica graduale della posizione, della larghezza e dell'altezza di un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="24759-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="24759-108">Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearRectKeyFrame> creare una transizione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="24759-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="24759-109">Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> classe per ridurre improvvisamente l'altezza del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="24759-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="24759-110">I fotogrammi chiave discreti <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> , ad esempio, creano modifiche improvvise tra i valori, ovvero la riduzione dell'altezza si verifica rapidamente e non è un'operazione impercettibile.</span><span class="sxs-lookup"><span data-stu-id="24759-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="24759-111">Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineRectKeyFrame> classe per ripristinare le dimensioni e la posizione originali del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="24759-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="24759-112">Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineRectKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="24759-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="24759-113">In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="24759-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="24759-114">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="24759-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24759-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24759-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="24759-116">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="24759-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="24759-117">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="24759-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
