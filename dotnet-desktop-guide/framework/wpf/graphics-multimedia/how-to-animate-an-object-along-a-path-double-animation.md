---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Double)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966913"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="9ca5a-102">Procedura: animare un oggetto lungo un percorso (animazione Double)</span><span class="sxs-lookup"><span data-stu-id="9ca5a-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="9ca5a-103">Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> classe per spostare un oggetto lungo un tracciato definito da un oggetto <xref:System.Windows.Media.PathGeometry> .</span><span class="sxs-lookup"><span data-stu-id="9ca5a-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ca5a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ca5a-104">Example</span></span>  
 <span data-ttu-id="9ca5a-105">Nell'esempio seguente vengono usati due <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un tracciato geometrico:</span><span class="sxs-lookup"><span data-stu-id="9ca5a-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="9ca5a-106">Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione all'oggetto <xref:System.Windows.Media.TranslateTransform.X%2A> dell'oggetto <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9ca5a-107">In questo modo il rettangolo si sposta orizzontalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="9ca5a-108">Il secondo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione dell'oggetto <xref:System.Windows.Media.TranslateTransform.Y%2A> <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="9ca5a-109">In questo modo il rettangolo si sposta verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="9ca5a-110">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="9ca5a-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="9ca5a-111">Un altro modo per spostare un oggetto usando un percorso geometrico consiste nell'usare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9ca5a-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="9ca5a-112">Per un esempio, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="9ca5a-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca5a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ca5a-113">See also</span></span>

- [<span data-ttu-id="9ca5a-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="9ca5a-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9ca5a-115">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="9ca5a-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
