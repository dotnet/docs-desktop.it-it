---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Point)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966904"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="4812c-102">Procedura: animare un oggetto lungo un percorso (animazione Point)</span><span class="sxs-lookup"><span data-stu-id="4812c-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="4812c-103">Questo esempio illustra come usare un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto per animare un oggetto <xref:System.Windows.Point> lungo un tracciato curvo.</span><span class="sxs-lookup"><span data-stu-id="4812c-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4812c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4812c-104">Example</span></span>  
 <span data-ttu-id="4812c-105">Nell'esempio seguente viene spostato un oggetto <xref:System.Windows.Media.EllipseGeometry> lungo un tracciato definito da un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="4812c-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4812c-106">La proprietà della geometria dell'ellisse <xref:System.Windows.Media.EllipseGeometry.Center%2A> , che accetta un <xref:System.Windows.Point> valore, ne specifica la posizione; per spostare la geometria dell'ellisse, animarne la <xref:System.Windows.Media.EllipseGeometry.Center%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4812c-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="4812c-107">Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto per animare la <xref:System.Windows.Media.EllipseGeometry> proprietà dell'oggetto <xref:System.Windows.Media.EllipseGeometry.Center%2A> .</span><span class="sxs-lookup"><span data-stu-id="4812c-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="4812c-108">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="4812c-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="4812c-109">La versione del codice dell'esempio precedente usava un oggetto <xref:System.Windows.Media.Animation.Storyboard> per animare <xref:System.Windows.Media.EllipseGeometry> , anche se è stata applicata una sola animazione.</span><span class="sxs-lookup"><span data-stu-id="4812c-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="4812c-110">Un <xref:System.Windows.Media.Animation.Storyboard> è spesso il modo più semplice per applicare più animazioni perché queste animazioni possono essere controllate dallo stesso <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="4812c-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="4812c-111">Tuttavia, un modo più semplice per applicare una singola animazione a una proprietà quando si usa il codice consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4812c-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="4812c-112">Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="4812c-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4812c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4812c-113">See also</span></span>

- [<span data-ttu-id="4812c-114">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="4812c-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="4812c-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="4812c-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="4812c-116">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="4812c-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
