---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969877"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="0accd-102">Procedura: far ruotare sul posto un elemento</span><span class="sxs-lookup"><span data-stu-id="0accd-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="0accd-103">In questo esempio viene illustrato come eseguire la rotazione di un elemento utilizzando un oggetto <xref:System.Windows.Media.RotateTransform> e un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> .</span><span class="sxs-lookup"><span data-stu-id="0accd-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="0accd-104">Nell'esempio seguente viene applicato alla <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0accd-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="0accd-105">Nell'esempio viene utilizzato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare l'oggetto <xref:System.Windows.Media.RotateTransform.Angle%2A> di <xref:System.Windows.Media.RotateTransform> .</span><span class="sxs-lookup"><span data-stu-id="0accd-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="0accd-106">Per far ruotare l'elemento, nell'esempio viene impostata la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento sul punto (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="0accd-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0accd-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0accd-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="0accd-108">Per l'esempio completo, che include altri esempi di trasformazione, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="0accd-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0accd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0accd-109">See also</span></span>

- [<span data-ttu-id="0accd-110">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="0accd-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0accd-111">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="0accd-111">Transforms Overview</span></span>](transforms-overview.md)
