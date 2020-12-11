---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969268"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="b7b21-102">Procedura: ruotare un oggetto utilizzando un percorso geometrico</span><span class="sxs-lookup"><span data-stu-id="b7b21-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="b7b21-103">Questo esempio illustra come ruotare (pivot) un oggetto lungo un tracciato geometrico definito da un <xref:System.Windows.Media.PathGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b7b21-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7b21-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7b21-104">Example</span></span>  
 <span data-ttu-id="b7b21-105">Nell'esempio seguente vengono utilizzati tre <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un tracciato geometrico.</span><span class="sxs-lookup"><span data-stu-id="b7b21-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="b7b21-106">Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione a un oggetto <xref:System.Windows.Media.RotateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b7b21-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="b7b21-107">L'animazione genera valori angolari.</span><span class="sxs-lookup"><span data-stu-id="b7b21-107">The animation generates angle values.</span></span> <span data-ttu-id="b7b21-108">Il rettangolo ruota lungo i contorni del tracciato.</span><span class="sxs-lookup"><span data-stu-id="b7b21-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="b7b21-109">Gli altri due oggetti animano i <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform.Y%2A> valori e di un oggetto <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b7b21-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="b7b21-110">Fanno in modo che il rettangolo si sposti orizzontalmente e verticalmente lungo il tracciato.</span><span class="sxs-lookup"><span data-stu-id="b7b21-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="b7b21-111">Un altro modo per ruotare un oggetto usando un percorso geometrico consiste nell'usare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto e impostare la relativa <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="b7b21-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="b7b21-112">Per ulteriori informazioni e un esempio, vedere [ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="b7b21-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="b7b21-113">Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="b7b21-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b21-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7b21-114">See also</span></span>

- [<span data-ttu-id="b7b21-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="b7b21-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b7b21-116">Path Animation Sample (Esempio di animazione tracciato)</span><span class="sxs-lookup"><span data-stu-id="b7b21-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="b7b21-117">Procedure relative all'animazione percorso</span><span class="sxs-lookup"><span data-stu-id="b7b21-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
