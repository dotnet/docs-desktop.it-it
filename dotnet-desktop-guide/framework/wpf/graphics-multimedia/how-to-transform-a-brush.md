---
title: 'Procedura: trasformare un oggetto Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965566"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="3a253-102">Procedura: trasformare un oggetto Brush</span><span class="sxs-lookup"><span data-stu-id="3a253-102">How to: Transform a Brush</span></span>
<span data-ttu-id="3a253-103">Questo esempio illustra come trasformare <xref:System.Windows.Media.Brush> oggetti usando le due proprietà di trasformazione seguenti: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="3a253-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="3a253-104">Negli esempi seguenti viene usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare il contenuto di un oggetto <xref:System.Windows.Media.ImageBrush> di 45 gradi.</span><span class="sxs-lookup"><span data-stu-id="3a253-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="3a253-105">Nella figura seguente viene illustrato l'oggetto <xref:System.Windows.Media.ImageBrush> senza un oggetto <xref:System.Windows.Media.RotateTransform> , con l'oggetto <xref:System.Windows.Media.RotateTransform> applicato alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con l'oggetto <xref:System.Windows.Media.RotateTransform> applicato alla <xref:System.Windows.Media.Brush.Transform%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a253-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="3a253-106">![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="3a253-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a253-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a253-107">Example</span></span>  
 <span data-ttu-id="3a253-108">Nel primo esempio viene applicato un oggetto <xref:System.Windows.Media.RotateTransform> alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un oggetto <xref:System.Windows.Media.ImageBrush> .</span><span class="sxs-lookup"><span data-stu-id="3a253-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="3a253-109">Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e di un <xref:System.Windows.Media.RotateTransform> oggetto sono entrambe impostate su 0,5, ovvero sulla coordinata relativa del punto centrale di questo contenuto.</span><span class="sxs-lookup"><span data-stu-id="3a253-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="3a253-110">Di conseguenza, il <xref:System.Windows.Media.ImageBrush> contenuto ruota attorno al centro.</span><span class="sxs-lookup"><span data-stu-id="3a253-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="3a253-111">Nel secondo esempio viene anche applicato un oggetto <xref:System.Windows.Media.RotateTransform> a un oggetto. <xref:System.Windows.Media.ImageBrush> tuttavia, in questo esempio viene utilizzata la <xref:System.Windows.Media.Brush.Transform%2A> proprietà anziché la <xref:System.Windows.Media.Brush.RelativeTransform%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a253-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="3a253-112">Per ruotare il pennello intorno al relativo centro, l'esempio imposta <xref:System.Windows.Media.RotateTransform.CenterX%2A> le <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e dell' <xref:System.Windows.Media.RotateTransform> oggetto su coordinate assolute.</span><span class="sxs-lookup"><span data-stu-id="3a253-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="3a253-113">Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="3a253-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="3a253-114">Per una descrizione del funzionamento delle <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> proprietà e, vedere [Cenni preliminari sulla trasformazione dei pennelli](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3a253-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="3a253-115">Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="3a253-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="3a253-116">Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3a253-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a253-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a253-117">See also</span></span>

- [<span data-ttu-id="3a253-118">Cenni preliminari sulle proprietà di trasformazione Brush</span><span class="sxs-lookup"><span data-stu-id="3a253-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="3a253-119">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="3a253-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="3a253-120">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="3a253-120">Transforms Overview</span></span>](transforms-overview.md)
