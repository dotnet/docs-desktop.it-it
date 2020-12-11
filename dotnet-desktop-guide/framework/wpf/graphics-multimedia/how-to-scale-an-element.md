---
title: 'Procedura: ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967015"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="9e9af-102">Procedura: ridimensionare un elemento</span><span class="sxs-lookup"><span data-stu-id="9e9af-102">How to: Scale an Element</span></span>
<span data-ttu-id="9e9af-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="9e9af-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="9e9af-104">Usare le <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e per ridimensionare l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="9e9af-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="9e9af-105">Il valore 1,5, ad esempio, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> estende l'elemento al 150% della larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="9e9af-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="9e9af-106"><xref:System.Windows.Media.ScaleTransform.ScaleY%2A>Il valore 0,5 compatta l'altezza di un elemento del 50%.</span><span class="sxs-lookup"><span data-stu-id="9e9af-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="9e9af-107">Usare le <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà e per specificare il punto centrale dell'operazione di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="9e9af-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="9e9af-108">Per impostazione predefinita, un oggetto <xref:System.Windows.Media.ScaleTransform> viene centrato al punto (0, 0), che corrisponde all'angolo superiore sinistro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9e9af-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="9e9af-109">Questo ha l'effetto di trasferire l'elemento e anche di renderlo più grande, perché quando si applica un <xref:System.Windows.Media.Transform> , si modifica lo spazio delle coordinate in cui si trova l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9e9af-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="9e9af-110">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.ScaleTransform> per raddoppiare le dimensioni di un 50 per 50 <xref:System.Windows.Shapes.Rectangle> .</span><span class="sxs-lookup"><span data-stu-id="9e9af-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="9e9af-111">Il <xref:System.Windows.Media.ScaleTransform> valore di è 0 (impostazione predefinita) per <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> .</span><span class="sxs-lookup"><span data-stu-id="9e9af-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e9af-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e9af-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="9e9af-113">In genere, si impostano <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto ridimensionato: ( <xref:System.Windows.FrameworkElement.Width%2A> /2, <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="9e9af-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="9e9af-114">Nell'esempio seguente viene illustrato un altro oggetto di <xref:System.Windows.Shapes.Rectangle> dimensioni raddoppiate. Tuttavia, il <xref:System.Windows.Media.ScaleTransform> valore di è 25 per <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> , che corrisponde al centro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9e9af-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="9e9af-115">Nella figura seguente viene illustrata la differenza tra le due <xref:System.Windows.Media.ScaleTransform> operazioni.</span><span class="sxs-lookup"><span data-stu-id="9e9af-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="9e9af-116">La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="9e9af-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="9e9af-117">![Ridimensionamenti con raddoppiamento di valore con punti centrali diversi](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="9e9af-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="9e9af-118">Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi</span><span class="sxs-lookup"><span data-stu-id="9e9af-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="9e9af-119">Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="9e9af-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9af-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e9af-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="9e9af-121">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="9e9af-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="9e9af-122">Procedure</span><span class="sxs-lookup"><span data-stu-id="9e9af-122">How-to Topics</span></span>](transformations-how-to-topics.md)
