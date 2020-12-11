---
title: 'Procedura: disegnare un’immagine con ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951254"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="2df04-102">Procedura: disegnare un’immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="2df04-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="2df04-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ImageDrawing> per creare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="2df04-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="2df04-104">Un oggetto <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un oggetto <xref:System.Windows.Media.ImageSource> con <xref:System.Windows.Media.DrawingBrush> , <xref:System.Windows.Media.DrawingImage> o <xref:System.Windows.Media.Visual> .</span><span class="sxs-lookup"><span data-stu-id="2df04-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="2df04-105">Per creare un'immagine, è necessario creare un oggetto <xref:System.Windows.Media.ImageDrawing> e impostare le relative <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà e.</span><span class="sxs-lookup"><span data-stu-id="2df04-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="2df04-106">La <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da creare e la <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e le dimensioni di ogni immagine.</span><span class="sxs-lookup"><span data-stu-id="2df04-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df04-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2df04-107">Example</span></span>  
 <span data-ttu-id="2df04-108">Nell'esempio seguente viene creato un disegno composito utilizzando quattro <xref:System.Windows.Media.ImageDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="2df04-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="2df04-109">Questo esempio genera l'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="2df04-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="2df04-110">![Alcuni oggetti DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="2df04-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="2df04-111">Quattro oggetti ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="2df04-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="2df04-112">Per un esempio in cui viene illustrato un modo semplice per visualizzare un'immagine senza usare <xref:System.Windows.Media.ImageDrawing> , vedere [usare l'elemento Image](../controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="2df04-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df04-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2df04-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="2df04-114">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="2df04-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="2df04-115">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="2df04-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="2df04-116">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="2df04-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
