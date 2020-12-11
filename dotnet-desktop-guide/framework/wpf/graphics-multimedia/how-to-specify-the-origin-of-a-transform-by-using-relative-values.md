---
title: "Procedura: specificare l'origine di una trasformazione utilizzando valori relativi"
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961276"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="24b7c-102">Procedura: specificare l'origine di una trasformazione utilizzando valori relativi</span><span class="sxs-lookup"><span data-stu-id="24b7c-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="24b7c-103">In questo esempio viene illustrato come utilizzare valori relativi per specificare l'origine di un oggetto <xref:System.Windows.UIElement.RenderTransform%2A> applicato a un oggetto <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="24b7c-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="24b7c-104">Quando si ruota, ridimensiona o inclina un oggetto utilizzando <xref:System.Windows.FrameworkElement> la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, l'impostazione predefinita applica la trasformazione all'angolo superiore sinistro dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="24b7c-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="24b7c-105">Se si desidera ruotare, ridimensionare o inclinare dal centro dell'elemento, è possibile compensare impostando il centro della trasformazione sul centro dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="24b7c-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="24b7c-106">Tuttavia, questa soluzione prevede che si conoscano le dimensioni dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="24b7c-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="24b7c-107">Un modo più semplice per applicare una trasformazione al centro di un elemento consiste nell'impostare la relativa <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su (0,5, 0,5), anziché impostare un valore centrale sulla trasformazione stessa.</span><span class="sxs-lookup"><span data-stu-id="24b7c-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24b7c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="24b7c-108">Example</span></span>  
 <span data-ttu-id="24b7c-109">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare di <xref:System.Windows.Controls.Button> 45 gradi in senso orario.</span><span class="sxs-lookup"><span data-stu-id="24b7c-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="24b7c-110">Poiché l'esempio non specifica un centro, il pulsante ruota intorno al punto (0, 0), ovvero l'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="24b7c-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="24b7c-111"><xref:System.Windows.Media.RotateTransform>Viene applicato alla <xref:System.Windows.UIElement.RenderTransform%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="24b7c-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="24b7c-112">La figura seguente mostra il risultato della trasformazione per l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="24b7c-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="24b7c-113">![Pulsante trasformato usando RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="24b7c-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="24b7c-114">Rotazione in senso orario di 45 gradi usando la proprietà RenderTransform</span><span class="sxs-lookup"><span data-stu-id="24b7c-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="24b7c-115">Nell'esempio seguente viene anche usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare di <xref:System.Windows.Controls.Button> 45 gradi in senso orario. in questo esempio l'oggetto <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante viene impostato su (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="24b7c-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="24b7c-116">Di conseguenza, la rotazione viene applicata al centro del pulsante anziché all'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="24b7c-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="24b7c-117">La figura seguente mostra il risultato della trasformazione per l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="24b7c-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="24b7c-118">![Pulsante trasformato rispetto al proprio centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="24b7c-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="24b7c-119">Rotazione di 45 gradi usando la proprietà RenderTransform con RenderTransformOrigin del valore di (0,5, 0,5)</span><span class="sxs-lookup"><span data-stu-id="24b7c-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="24b7c-120">Per ulteriori informazioni sulla trasformazione di <xref:System.Windows.FrameworkElement> oggetti, vedere [Cenni preliminari sulle trasformazioni](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="24b7c-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b7c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24b7c-121">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="24b7c-122">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="24b7c-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="24b7c-123">Procedure</span><span class="sxs-lookup"><span data-stu-id="24b7c-123">How-to Topics</span></span>](transformations-how-to-topics.md)
