---
title: 'Procedura: ruotare un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966889"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="61a82-102">Procedura: ruotare un oggetto</span><span class="sxs-lookup"><span data-stu-id="61a82-102">How to: Rotate an Object</span></span>
<span data-ttu-id="61a82-103">Questo esempio spiega come ruotare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="61a82-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="61a82-104">Nell'esempio viene prima creato un oggetto <xref:System.Windows.Media.RotateTransform> e quindi ne viene specificato il valore <xref:System.Windows.Media.RotateTransform.Angle%2A> in gradi.</span><span class="sxs-lookup"><span data-stu-id="61a82-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="61a82-105">Nell'esempio seguente viene ruotato un <xref:System.Windows.Shapes.Polyline> oggetto 45 gradi sull'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="61a82-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a82-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="61a82-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="61a82-107">Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e di <xref:System.Windows.Media.RotateTransform> specificano il punto su cui l'oggetto viene ruotato.</span><span class="sxs-lookup"><span data-stu-id="61a82-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="61a82-108">Il punto centrale viene espresso nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="61a82-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="61a82-109">Per impostazione predefinita, la rotazione viene applicata a (0,0), ovvero l'angolo superiore sinistro dell'oggetto da trasformare.</span><span class="sxs-lookup"><span data-stu-id="61a82-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="61a82-110">L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> oggetto in senso orario di 45 gradi sul punto (25, 50).</span><span class="sxs-lookup"><span data-stu-id="61a82-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="61a82-111">Nella figura seguente vengono illustrati i risultati dell'applicazione di un <xref:System.Windows.Media.Transform> ai due oggetti.</span><span class="sxs-lookup"><span data-stu-id="61a82-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="61a82-112">![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="61a82-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="61a82-113">Due oggetti che ruotano di 45 gradi da centri di rotazione diversi</span><span class="sxs-lookup"><span data-stu-id="61a82-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="61a82-114">Negli <xref:System.Windows.Shapes.Polyline> esempi precedenti è un oggetto <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="61a82-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="61a82-115">Quando si applica un oggetto <xref:System.Windows.Media.Transform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un oggetto <xref:System.Windows.UIElement> , è possibile utilizzare la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà per specificare un'origine per ogni oggetto <xref:System.Windows.Media.Transform> che si applica all'elemento.</span><span class="sxs-lookup"><span data-stu-id="61a82-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="61a82-116">Poiché la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà utilizza coordinate relative, è possibile applicare una trasformazione al centro dell'elemento anche se non si conoscono le relative dimensioni.</span><span class="sxs-lookup"><span data-stu-id="61a82-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="61a82-117">Per ulteriori informazioni e per un esempio, vedere [specificare l'origine di una trasformazione utilizzando valori relativi](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="61a82-118">Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="61a82-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a82-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a82-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="61a82-120">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="61a82-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="61a82-121">Procedure</span><span class="sxs-lookup"><span data-stu-id="61a82-121">How-to Topics</span></span>](transformations-how-to-topics.md)
