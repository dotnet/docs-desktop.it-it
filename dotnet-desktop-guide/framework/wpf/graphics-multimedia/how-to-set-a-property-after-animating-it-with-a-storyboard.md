---
title: 'Procedura: impostare una proprietà dopo averla animata con uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965590"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="4ac26-102">Procedura: impostare una proprietà dopo averla animata con uno storyboard</span><span class="sxs-lookup"><span data-stu-id="4ac26-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="4ac26-103">In alcuni casi, potrebbe sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata.</span><span class="sxs-lookup"><span data-stu-id="4ac26-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ac26-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ac26-104">Example</span></span>  
 <span data-ttu-id="4ac26-105">Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> viene usato un oggetto per animare il colore di un oggetto <xref:System.Windows.Media.SolidColorBrush> .</span><span class="sxs-lookup"><span data-stu-id="4ac26-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="4ac26-106">Lo storyboard viene attivato quando si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="4ac26-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="4ac26-107">L' <xref:System.Windows.Media.Animation.Timeline.Completed> evento viene gestito in modo che il programma riceva una notifica al <xref:System.Windows.Media.Animation.ColorAnimation> termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4ac26-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="4ac26-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ac26-108">Example</span></span>  
 <span data-ttu-id="4ac26-109">Al termine dell' <xref:System.Windows.Media.Animation.ColorAnimation> operazione, il programma tenta di modificare il colore del pennello in blu.</span><span class="sxs-lookup"><span data-stu-id="4ac26-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="4ac26-110">Il codice precedente non sembra eseguire alcuna operazione: il pennello rimane giallo, che corrisponde al valore fornito dall'oggetto <xref:System.Windows.Media.Animation.ColorAnimation> che ha animato il pennello.</span><span class="sxs-lookup"><span data-stu-id="4ac26-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="4ac26-111">Il valore della proprietà sottostante (valore di base) viene effettivamente modificato in blu.</span><span class="sxs-lookup"><span data-stu-id="4ac26-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="4ac26-112">Tuttavia, il valore effettivo, o corrente, rimane giallo perché <xref:System.Windows.Media.Animation.ColorAnimation> sta ancora eseguendo l'override del valore di base.</span><span class="sxs-lookup"><span data-stu-id="4ac26-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="4ac26-113">Se si desidera che il valore di base diventi di nuovo il valore effettivo, è necessario arrestare l'animazione dall'influire sulla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ac26-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="4ac26-114">Esistono tre modi per eseguire questa operazione con le animazioni storyboard:</span><span class="sxs-lookup"><span data-stu-id="4ac26-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="4ac26-115">Impostare la proprietà dell'animazione <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> su <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="4ac26-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="4ac26-116">Rimuovere l'intero storyboard.</span><span class="sxs-lookup"><span data-stu-id="4ac26-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="4ac26-117">Rimuovere l'animazione dalla singola proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ac26-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="4ac26-118">Impostare la proprietà FillBehavior dell'animazione su Stop</span><span class="sxs-lookup"><span data-stu-id="4ac26-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="4ac26-119">Impostando <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> su <xref:System.Windows.Media.Animation.FillBehavior.Stop> , si indica all'animazione di arrestare l'effetto della proprietà di destinazione dopo che ha raggiunto la fine del periodo attivo.</span><span class="sxs-lookup"><span data-stu-id="4ac26-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="4ac26-120">Rimuovere l'intero storyboard</span><span class="sxs-lookup"><span data-stu-id="4ac26-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="4ac26-121">Utilizzando un <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger o il <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> metodo, si indica alle animazioni dello storyboard di interrompere l'influire sulle proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4ac26-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="4ac26-122">La differenza tra questo approccio e l'impostazione della <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà è che è possibile rimuovere lo storyboard in qualsiasi momento, mentre la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà ha effetto solo quando l'animazione raggiunge la fine del periodo attivo.</span><span class="sxs-lookup"><span data-stu-id="4ac26-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="4ac26-123">Rimuovere un'animazione da una singola proprietà</span><span class="sxs-lookup"><span data-stu-id="4ac26-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="4ac26-124">Un'altra tecnica per arrestare un'animazione dall'effetto di una proprietà consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo dell'oggetto a cui si sta aggiungendo un'animazione.</span><span class="sxs-lookup"><span data-stu-id="4ac26-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="4ac26-125">Specificare la proprietà che viene animata come primo parametro e `null` come secondo.</span><span class="sxs-lookup"><span data-stu-id="4ac26-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="4ac26-126">Questa tecnica funziona anche per le animazioni non Storyboard.</span><span class="sxs-lookup"><span data-stu-id="4ac26-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac26-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ac26-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="4ac26-128">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="4ac26-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="4ac26-129">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="4ac26-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
