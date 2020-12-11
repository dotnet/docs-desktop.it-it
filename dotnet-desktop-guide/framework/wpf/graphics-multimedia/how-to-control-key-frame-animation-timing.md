---
title: 'Procedura: controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968056"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="7429e-102">Procedura: controllare la durata delle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7429e-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="7429e-103">Questo esempio illustra come controllare l'intervallo dei fotogrammi chiave all'interno di un'animazione con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="7429e-104">Analogamente ad altre animazioni, le animazioni con fotogrammi chiave hanno una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="7429e-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="7429e-105">Oltre a specificare la durata di un'animazione, è necessario specificare la parte di tale durata assegnata a ognuno dei fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="7429e-106">Per assegnare l'ora, specificare un <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave nell'animazione.</span><span class="sxs-lookup"><span data-stu-id="7429e-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="7429e-107"><xref:System.Windows.Media.Animation.KeyTime>Per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica l'intervallo di tempo in cui un fotogramma chiave viene riprodotto).</span><span class="sxs-lookup"><span data-stu-id="7429e-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="7429e-108">È possibile specificare <xref:System.Windows.Media.Animation.KeyTime> come <xref:System.TimeSpan> valore, come percentuale, o come <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valore speciale.</span><span class="sxs-lookup"><span data-stu-id="7429e-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="7429e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7429e-109">Example</span></span>

<span data-ttu-id="7429e-110">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> per animare un rettangolo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="7429e-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="7429e-111">Gli orari delle chiavi dei fotogrammi chiave vengono impostati con <xref:System.TimeSpan> i valori.</span><span class="sxs-lookup"><span data-stu-id="7429e-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="7429e-112">Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="7429e-113">![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="7429e-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="7429e-114">Nell'esempio seguente viene illustrata un'animazione identica, ad eccezione del fatto che le chiavi temporali dei fotogrammi chiave sono impostate con valori percentuali.</span><span class="sxs-lookup"><span data-stu-id="7429e-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="7429e-115">Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="7429e-116">![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="7429e-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="7429e-117">Nell'esempio seguente vengono usati <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> i valori della chiave temporale.</span><span class="sxs-lookup"><span data-stu-id="7429e-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="7429e-118">Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="7429e-119">![I valori dei fotogrammi chiave vengono raggiunti a 3,3, 6,6 e 9,9 secondi](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="7429e-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="7429e-120">Nell'esempio finale vengono usati <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> i valori della chiave temporale.</span><span class="sxs-lookup"><span data-stu-id="7429e-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="7429e-121">Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.</span><span class="sxs-lookup"><span data-stu-id="7429e-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="7429e-122">![I valori dei fotogrammi chiave vengono raggiunti a 0, 5 e 10 secondi](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="7429e-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="7429e-123">Per semplicità, le versioni del codice di questo esempio usano animazioni locali, non Storyboard, perché solo una singola animazione viene applicata a una singola proprietà, ma gli esempi possono essere modificati per usare gli storyboard.</span><span class="sxs-lookup"><span data-stu-id="7429e-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="7429e-124">Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="7429e-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="7429e-125">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="7429e-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="7429e-126">Per ulteriori informazioni sulle animazioni con fotogramma chiave, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7429e-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7429e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7429e-127">See also</span></span>

- [<span data-ttu-id="7429e-128">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7429e-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7429e-129">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="7429e-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7429e-130">Procedure</span><span class="sxs-lookup"><span data-stu-id="7429e-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
