---
title: "Procedura: disegnare un'area con un video"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968743"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="169f7-102">Procedura: disegnare un'area con un video</span><span class="sxs-lookup"><span data-stu-id="169f7-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="169f7-103">Questo esempio illustra come disegnare un'area con supporti.</span><span class="sxs-lookup"><span data-stu-id="169f7-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="169f7-104">Un modo per disegnare un'area con supporti consiste nell'usare un <xref:System.Windows.Controls.MediaElement> insieme a un <xref:System.Windows.Media.VisualBrush> .</span><span class="sxs-lookup"><span data-stu-id="169f7-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="169f7-105">Utilizzare <xref:System.Windows.Controls.MediaElement> per caricare e riprodurre i supporti, quindi utilizzarlo per impostare la <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà dell'oggetto <xref:System.Windows.Media.VisualBrush> .</span><span class="sxs-lookup"><span data-stu-id="169f7-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="169f7-106">È quindi possibile usare <xref:System.Windows.Media.VisualBrush> per disegnare un'area con il supporto caricato.</span><span class="sxs-lookup"><span data-stu-id="169f7-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="169f7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="169f7-107">Example</span></span>  
 <span data-ttu-id="169f7-108">Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Controls.MediaElement> e un oggetto <xref:System.Windows.Media.VisualBrush> per disegnare l'oggetto <xref:System.Windows.Controls.TextBlock.Foreground%2A> di un <xref:System.Windows.Controls.TextBlock> controllo con video.</span><span class="sxs-lookup"><span data-stu-id="169f7-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="169f7-109">In questo esempio la <xref:System.Windows.Controls.MediaElement.IsMuted%2A> proprietà di viene impostata <xref:System.Windows.Controls.MediaElement> su in `true` modo che non produca alcun suono.</span><span class="sxs-lookup"><span data-stu-id="169f7-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="169f7-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="169f7-110">Example</span></span>  
 <span data-ttu-id="169f7-111">Poiché <xref:System.Windows.Media.VisualBrush> eredita dalla <xref:System.Windows.Media.TileBrush> classe, fornisce diverse modalità di affiancamento.</span><span class="sxs-lookup"><span data-stu-id="169f7-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="169f7-112">Impostando la <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.VisualBrush> su e impostando la <xref:System.Windows.Media.TileMode.Tile> relativa <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà su un valore più piccolo dell'area da disegnare, è possibile creare un modello affiancato.</span><span class="sxs-lookup"><span data-stu-id="169f7-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="169f7-113">L'esempio seguente è identico all'esempio precedente, ad eccezione del fatto che <xref:System.Windows.Media.VisualBrush> genera un modello dal video.</span><span class="sxs-lookup"><span data-stu-id="169f7-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="169f7-114">Per informazioni sull'aggiunta di un file di contenuto, ad esempio un file multimediale, all'applicazione, vedere la pagina relativa ai [file di dati, di contenuto e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="169f7-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="169f7-115">Quando si aggiunge un file multimediale, è necessario aggiungerlo come file di contenuto, non come file di risorse.</span><span class="sxs-lookup"><span data-stu-id="169f7-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169f7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="169f7-116">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="169f7-117">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="169f7-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="169f7-118">Cenni preliminari sugli oggetti TileBrush</span><span class="sxs-lookup"><span data-stu-id="169f7-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="169f7-119">Panoramica delle funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="169f7-119">Multimedia Overview</span></span>](multimedia-overview.md)
