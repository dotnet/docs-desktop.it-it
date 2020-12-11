---
title: 'Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967852"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="bb9ed-102">Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente</span><span class="sxs-lookup"><span data-stu-id="bb9ed-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="bb9ed-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ScaleTransform> per capovolgere <xref:System.Windows.UIElement> orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="bb9ed-104">In questo esempio un <xref:System.Windows.Controls.Button> controllo (un tipo di <xref:System.Windows.UIElement> ) viene capovolto applicando un oggetto <xref:System.Windows.Media.ScaleTransform> alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb9ed-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb9ed-105">Example</span></span>  
 <span data-ttu-id="bb9ed-106">Nella figura seguente viene illustrato il pulsante da capovolgere.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="bb9ed-107">![Pulsante senza trasformazioni](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="bb9ed-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="bb9ed-108">UIElement da capovolgere</span><span class="sxs-lookup"><span data-stu-id="bb9ed-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="bb9ed-109">Di seguito viene illustrato il codice che crea il pulsante.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="bb9ed-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb9ed-110">Example</span></span>  
 <span data-ttu-id="bb9ed-111">Per capovolgere il pulsante orizzontalmente, creare un oggetto <xref:System.Windows.Media.ScaleTransform> e impostare la relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà su-1.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="bb9ed-112">Applicare l'oggetto <xref:System.Windows.Media.ScaleTransform> alla proprietà del pulsante <xref:System.Windows.UIElement.RenderTransform%2A> .</span><span class="sxs-lookup"><span data-stu-id="bb9ed-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="bb9ed-113">![Pulsante capovolto orizzontalmente intorno &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="bb9ed-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="bb9ed-114">Pulsante dopo l'applicazione di ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="bb9ed-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb9ed-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb9ed-115">Example</span></span>  
 <span data-ttu-id="bb9ed-116">Come si può notare dalla figura precedente, il pulsante è stato capovolto, ma è stato spostato.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="bb9ed-117">Questo perché il pulsante è stato capovolto dall'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="bb9ed-118">Per capovolgere il pulsante sul posto, è necessario applicare al <xref:System.Windows.Media.ScaleTransform> centro, non all'angolo.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="bb9ed-119">Un modo semplice per applicare al <xref:System.Windows.Media.ScaleTransform> Centro pulsanti consiste nell'impostare la proprietà del pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> su 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="bb9ed-120">![Pulsante capovolto orizzontalmente rispetto al proprio centro](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="bb9ed-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="bb9ed-121">Pulsante con RenderTransformOrigin 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="bb9ed-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb9ed-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb9ed-122">Example</span></span>  
 <span data-ttu-id="bb9ed-123">Per capovolgere il pulsante verticalmente, impostare la <xref:System.Windows.Media.ScaleTransform> proprietà dell'oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> invece della relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="bb9ed-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="bb9ed-124">![Pulsante capovolto verticalmente rispetto al proprio centro](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="bb9ed-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="bb9ed-125">Pulsante capovolto verticalmente</span><span class="sxs-lookup"><span data-stu-id="bb9ed-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9ed-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb9ed-126">See also</span></span>

- [<span data-ttu-id="bb9ed-127">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="bb9ed-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
