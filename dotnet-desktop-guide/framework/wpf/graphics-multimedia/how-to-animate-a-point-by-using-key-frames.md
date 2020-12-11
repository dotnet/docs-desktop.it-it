---
title: 'Procedura: animare un punto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967018"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="b0e1c-102">Procedura: animare un punto utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="b0e1c-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="b0e1c-103">Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe per aggiungere un'animazione a <xref:System.Windows.Point> .</span><span class="sxs-lookup"><span data-stu-id="b0e1c-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e1c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0e1c-104">Example</span></span>  
 <span data-ttu-id="b0e1c-105">L'esempio seguente sposta un'ellisse lungo un tracciato triangolare.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="b0e1c-106">Nell'esempio viene utilizzata la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà di un oggetto <xref:System.Windows.Media.EllipseGeometry> .</span><span class="sxs-lookup"><span data-stu-id="b0e1c-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="b0e1c-107">Questa animazione usa tre fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b0e1c-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="b0e1c-108">Durante il primo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.LinearPointKeyFrame> classe per spostare l'ellisse lungo un tracciato a una velocità costante dalla posizione iniziale.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="b0e1c-109">Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearPointKeyFrame> creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="b0e1c-110">Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> classe per spostare improvvisamente l'ellisse lungo il percorso alla posizione successiva.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="b0e1c-111">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> creare salti improvvisi tra i valori.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="b0e1c-112">Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplinePointKeyFrame> classe per spostare nuovamente l'ellisse nella posizione iniziale.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="b0e1c-113">Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplinePointKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b0e1c-114">In questo esempio, l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.</span><span class="sxs-lookup"><span data-stu-id="b0e1c-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b0e1c-115">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="b0e1c-115">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
 <span data-ttu-id="b0e1c-116">Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> .</span><span class="sxs-lookup"><span data-stu-id="b0e1c-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="b0e1c-117">Tuttavia, quando si applica un'unica animazione nel codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="b0e1c-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="b0e1c-118">Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="b0e1c-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e1c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0e1c-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="b0e1c-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="b0e1c-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b0e1c-121">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="b0e1c-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
