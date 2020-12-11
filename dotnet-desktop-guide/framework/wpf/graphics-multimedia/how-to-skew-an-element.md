---
title: 'Procedura: inclinare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961291"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="e417f-102">Procedura: inclinare un elemento</span><span class="sxs-lookup"><span data-stu-id="e417f-102">How to: Skew an Element</span></span>
<span data-ttu-id="e417f-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.SkewTransform> per inclinare un elemento.</span><span class="sxs-lookup"><span data-stu-id="e417f-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="e417f-104">L'inclinazione, nota anche come distorsione, è una trasformazione che adatta lo spazio delle coordinate in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="e417f-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="e417f-105">Un utilizzo tipico di un oggetto <xref:System.Windows.Media.SkewTransform> è per la simulazione della profondità 3D negli oggetti 2D.</span><span class="sxs-lookup"><span data-stu-id="e417f-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="e417f-106">Usare le <xref:System.Windows.Media.SkewTransform.CenterX%2A> <xref:System.Windows.Media.SkewTransform.CenterY%2A> proprietà e per specificare il punto centrale di <xref:System.Windows.Media.SkewTransform> .</span><span class="sxs-lookup"><span data-stu-id="e417f-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="e417f-107">Usare le <xref:System.Windows.Media.SkewTransform.AngleX%2A> <xref:System.Windows.Media.SkewTransform.AngleY%2A> proprietà e per specificare l'angolo di inclinazione dell'asse x e l'asse y e per inclinare il sistema di coordinate corrente lungo questi assi.</span><span class="sxs-lookup"><span data-stu-id="e417f-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="e417f-108">Per stimare l'effetto di una trasformazione asimmetria, tenere presente che <xref:System.Windows.Media.SkewTransform.AngleX%2A> inclina i valori dell'asse x rispetto al sistema di coordinate originale.</span><span class="sxs-lookup"><span data-stu-id="e417f-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="e417f-109">Pertanto, per un valore <xref:System.Windows.Media.SkewTransform.AngleX%2A> pari a 30, l'asse y ruota di 30 gradi attraverso l'origine e inclina i valori in x-by 30 gradi da tale origine.</span><span class="sxs-lookup"><span data-stu-id="e417f-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="e417f-110">Analogamente, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> valore pari a 30 inclina i valori y della forma di 30 gradi dall'origine.</span><span class="sxs-lookup"><span data-stu-id="e417f-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="e417f-111">Si noti che non si tratta dello stesso effetto ottenuto traslando (spostando) il sistema di coordinate di 30 gradi nell'asse x o y.</span><span class="sxs-lookup"><span data-stu-id="e417f-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="e417f-112">Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (0,0).</span><span class="sxs-lookup"><span data-stu-id="e417f-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e417f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e417f-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="e417f-114">Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25, 25).</span><span class="sxs-lookup"><span data-stu-id="e417f-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="e417f-115">L'esempio seguente applica un'inclinazione verticale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25, 25).</span><span class="sxs-lookup"><span data-stu-id="e417f-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="e417f-116">La figura seguente illustra le diverse inclinazioni usate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e417f-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="e417f-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="e417f-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="e417f-118">I tre esempi SkewTransform illustrati</span><span class="sxs-lookup"><span data-stu-id="e417f-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="e417f-119">Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="e417f-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e417f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e417f-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="e417f-121">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="e417f-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="e417f-122">Procedure</span><span class="sxs-lookup"><span data-stu-id="e417f-122">How-to Topics</span></span>](transformations-how-to-topics.md)
