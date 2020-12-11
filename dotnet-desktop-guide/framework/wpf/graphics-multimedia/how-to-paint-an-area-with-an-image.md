---
title: "Procedura: disegnare un'area con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963457"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="1bed1-102">Procedura: disegnare un'area con un'immagine</span><span class="sxs-lookup"><span data-stu-id="1bed1-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="1bed1-103">Questo esempio illustra come usare la <xref:System.Windows.Media.ImageBrush> classe per disegnare un'area con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="1bed1-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="1bed1-104">Un oggetto <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine, specificata dalla relativa <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1bed1-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bed1-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bed1-105">Example</span></span>  
 <span data-ttu-id="1bed1-106">Nell'esempio seguente viene disegnato l'oggetto <xref:System.Windows.Controls.Control.Background%2A> di un pulsante utilizzando un oggetto <xref:System.Windows.Media.ImageBrush> .</span><span class="sxs-lookup"><span data-stu-id="1bed1-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="1bed1-107">Per impostazione predefinita, un oggetto <xref:System.Windows.Media.ImageBrush> estende la propria immagine in modo da riempire completamente l'area che si sta disegnando.</span><span class="sxs-lookup"><span data-stu-id="1bed1-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="1bed1-108">Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine.</span><span class="sxs-lookup"><span data-stu-id="1bed1-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="1bed1-109">È possibile controllare questo comportamento impostando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di <xref:System.Windows.Media.TileBrush> su <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill> , che consente al pennello di mantenere le proporzioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="1bed1-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="1bed1-110">Se si impostano le <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà e di un <xref:System.Windows.Media.ImageBrush> , è possibile creare un modello ripetuto.</span><span class="sxs-lookup"><span data-stu-id="1bed1-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="1bed1-111">L'esempio seguente disegna un pulsante con un modello creato da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="1bed1-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="1bed1-112">Per altre informazioni sulla <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="1bed1-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="1bed1-113">Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.ImageBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="1bed1-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="1bed1-114">Per l'esempio completo, vedere [esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="1bed1-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bed1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bed1-115">See also</span></span>

- [<span data-ttu-id="1bed1-116">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="1bed1-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
