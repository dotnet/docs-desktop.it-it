---
title: 'Procedura: applicare una trasformazione a un elemento quando si verifica un evento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960817"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="d7e45-102">Procedura: applicare una trasformazione a un elemento quando si verifica un evento</span><span class="sxs-lookup"><span data-stu-id="d7e45-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="d7e45-103">Questo esempio illustra come applicare un oggetto <xref:System.Windows.Media.ScaleTransform> quando si verifica un evento.</span><span class="sxs-lookup"><span data-stu-id="d7e45-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="d7e45-104">Il concetto illustrato è identico a quello usato per applicare altri tipi di trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="d7e45-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="d7e45-105">Per ulteriori informazioni sui tipi di trasformazioni disponibili, vedere <xref:System.Windows.Media.Transform> Cenni preliminari sulla classe o sulle [trasformazioni](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d7e45-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="d7e45-106">È possibile applicare una trasformazione a un elemento in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7e45-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="d7e45-107">Se *non* si desidera che la trasformazione influisca sul layout, utilizzare la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d7e45-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="d7e45-108">Se si desidera che la trasformazione influisca sul layout, utilizzare la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d7e45-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="d7e45-109">Nell'esempio seguente viene applicato un oggetto <xref:System.Windows.Media.ScaleTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="d7e45-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="d7e45-110">Quando il mouse viene spostato sul pulsante, le <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e di <xref:System.Windows.Media.ScaleTransform> sono impostate su `2` , che determina un aumento delle dimensioni del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d7e45-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="d7e45-111">Quando il mouse viene spostato fuori dal pulsante <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> viene impostato su `1` , che fa sì che il pulsante ritorni alle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="d7e45-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e45-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7e45-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="d7e45-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7e45-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="d7e45-114">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="d7e45-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="d7e45-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="d7e45-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="d7e45-116">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="d7e45-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
