---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967066"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="8f9c2-102">Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)</span><span class="sxs-lookup"><span data-stu-id="8f9c2-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="8f9c2-103">Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> classe per animare un oggetto lungo un tracciato e fare in modo che l'animazione accumuli i valori di offset durante la ripetizione.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f9c2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f9c2-104">Example</span></span>  
 <span data-ttu-id="8f9c2-105">Nell'esempio seguente viene usato l' <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto per aggiungere un'animazione alla <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un oggetto <xref:System.Windows.Media.MatrixTransform> applicato a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="8f9c2-106">Di conseguenza, un pulsante si sposta lungo un tracciato curvo.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="8f9c2-107">Inoltre, nell'esempio la proprietà viene impostata <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> su `true` , in modo che l'offset della matrice animata si accumuli quando l'animazione si ripete.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="8f9c2-108">Poiché lo scostamento si accumula, il pulsante viene spostato ulteriormente sullo schermo quando l'animazione si ripete, piuttosto che tornare nella posizione iniziale.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="8f9c2-109">Si noti che, sebbene la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Proprietà provochi l'accumulo dei valori di offset nelle ripetizioni, non causa l'accumulo dei valori di rotazione.</span><span class="sxs-lookup"><span data-stu-id="8f9c2-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="8f9c2-110">Per aumentare l'accumulo dei valori di rotazione, impostare le <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà e dell'animazione <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> su `true` .</span><span class="sxs-lookup"><span data-stu-id="8f9c2-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="8f9c2-111">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="8f9c2-111">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="8f9c2-112">Per un esempio che illustra come animare un <xref:System.Windows.Media.Matrix> valore lungo un tracciato senza accumulo di offset, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="8f9c2-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9c2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9c2-113">See also</span></span>

- [<span data-ttu-id="8f9c2-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="8f9c2-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="8f9c2-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="8f9c2-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
