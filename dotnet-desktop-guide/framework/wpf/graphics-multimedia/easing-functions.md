---
title: Funzioni di interpolazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967699"
---
# <a name="easing-functions"></a><span data-ttu-id="afa86-102">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="afa86-102">Easing Functions</span></span>
<span data-ttu-id="afa86-103">Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="afa86-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="afa86-104">Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla.</span><span class="sxs-lookup"><span data-stu-id="afa86-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="afa86-105">È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.</span><span class="sxs-lookup"><span data-stu-id="afa86-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="afa86-106">Oltre a creare una funzione di interpolazione personalizzata ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase> , è possibile usare una delle diverse funzioni di interpolazione fornite dal runtime per creare effetti comuni.</span><span class="sxs-lookup"><span data-stu-id="afa86-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="afa86-107"><xref:System.Windows.Media.Animation.BackEase>: Ritrae leggermente il movimento di un'animazione prima di iniziare ad aggiungere un'animazione nel percorso indicato.</span><span class="sxs-lookup"><span data-stu-id="afa86-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="afa86-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="afa86-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="afa86-109"><xref:System.Windows.Media.Animation.CircleEase>: Crea un'animazione che accelera e/o decelera usando una funzione circolare.</span><span class="sxs-lookup"><span data-stu-id="afa86-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="afa86-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea un'animazione che accelera e/o decelera usando la formula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="afa86-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="afa86-111"><xref:System.Windows.Media.Animation.ElasticEase>: Crea un'animazione simile a una molla che oscilla avanti e indietro fino a quando non passa a Rest.</span><span class="sxs-lookup"><span data-stu-id="afa86-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="afa86-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Crea un'animazione che accelera e/o rallenta usando una formula esponenziale.</span><span class="sxs-lookup"><span data-stu-id="afa86-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="afa86-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea un'animazione che accelera e/o decelera usando la formula *f*(*t*) = *t*<sup>p</sup> dove p è uguale alla <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="afa86-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="afa86-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea un'animazione che accelera e/o decelera usando la formula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="afa86-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="afa86-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea un'animazione che accelera e/o decelera usando la formula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="afa86-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="afa86-116"><xref:System.Windows.Media.Animation.QuinticEase>: Crea un'animazione che accelera e/o decelera usando la formula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="afa86-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="afa86-117"><xref:System.Windows.Media.Animation.SineEase>: Crea un'animazione che accelera e/o rallenta usando una formula seno.</span><span class="sxs-lookup"><span data-stu-id="afa86-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="afa86-118">Per applicare una funzione di interpolazione a un'animazione, utilizzare la `EasingFunction` proprietà dell'animazione per specificare la funzione di interpolazione da applicare all'animazione.</span><span class="sxs-lookup"><span data-stu-id="afa86-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="afa86-119">Nell'esempio seguente viene applicata una <xref:System.Windows.Media.Animation.BounceEase> funzione di interpolazione a un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per creare un effetto di rimbalzo.</span><span class="sxs-lookup"><span data-stu-id="afa86-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="afa86-120">Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By.</span><span class="sxs-lookup"><span data-stu-id="afa86-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="afa86-121">Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="afa86-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="afa86-122">L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.</span><span class="sxs-lookup"><span data-stu-id="afa86-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="afa86-123">È possibile usare la <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> proprietà per modificare il comportamento della funzione di interpolazione, ovvero modificare la modalità di interpolazione dell'animazione.</span><span class="sxs-lookup"><span data-stu-id="afa86-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="afa86-124">Esistono tre possibili valori che è possibile assegnare per <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> :</span><span class="sxs-lookup"><span data-stu-id="afa86-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="afa86-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: L'interpolazione segue la formula matematica associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="afa86-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="afa86-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: L'interpolazione segue l'interpolazione del 100% meno l'output della formula associata alla funzione di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="afa86-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="afa86-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: L'interpolazione utilizza <xref:System.Windows.Media.Animation.EasingMode.EaseIn> per la prima metà dell'animazione e <xref:System.Windows.Media.Animation.EasingMode.EaseOut> per la seconda metà.</span><span class="sxs-lookup"><span data-stu-id="afa86-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="afa86-128">I grafici seguenti illustrano i diversi valori di <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> dove *f*(*x*) rappresenta lo stato di avanzamento dell'animazione e *t* rappresenta l'ora.</span><span class="sxs-lookup"><span data-stu-id="afa86-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="afa86-129">![Grafici di EasingMode per BackEase.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="afa86-130">![Grafici di EasingMode per BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="afa86-131">![Grafici di EasingMode per CircleEase.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="afa86-132">![Grafici di EasingMode per CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="afa86-133">![ElasticEase con grafici di EasingMode diversi.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="afa86-134">![Grafici di ExponentialEase con EasingMode diversi.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="afa86-135">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="afa86-136">![QuadraticEase con grafici di EasingMode diversi.](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="afa86-137">![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="afa86-138">![QuinticEase con grafici di EasingMode diversi.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="afa86-139">![SineEase per valori EasingMode diversi](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="afa86-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afa86-140">È possibile utilizzare <xref:System.Windows.Media.Animation.PowerEase> per creare lo stesso comportamento di <xref:System.Windows.Media.Animation.CubicEase> , <xref:System.Windows.Media.Animation.QuadraticEase> , <xref:System.Windows.Media.Animation.QuarticEase> e <xref:System.Windows.Media.Animation.QuinticEase> utilizzando la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="afa86-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="afa86-141">Se ad esempio si desidera utilizzare per <xref:System.Windows.Media.Animation.PowerEase> sostituire <xref:System.Windows.Media.Animation.CubicEase> , specificare un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valore pari a 3.</span><span class="sxs-lookup"><span data-stu-id="afa86-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="afa86-142">Oltre a usare le funzioni di interpolazione incluse in fase di esecuzione, è possibile creare funzioni di interpolazione personalizzate ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase> .</span><span class="sxs-lookup"><span data-stu-id="afa86-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="afa86-143">L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="afa86-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="afa86-144">È possibile aggiungere una logica matematica personalizzata per il comportamento della funzione di interpolazione eseguendo l'override del <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="afa86-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
