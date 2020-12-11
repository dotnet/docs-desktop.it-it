---
title: 'Procedura: codificare un oggetto Visual in un file di immagine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969883"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="3ae12-102">Procedura: codificare un oggetto Visual in un file di immagine</span><span class="sxs-lookup"><span data-stu-id="3ae12-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="3ae12-103">Questo esempio illustra come codificare un <xref:System.Windows.Media.Visual> oggetto in un file di immagine usando <xref:System.Windows.Media.Imaging.RenderTargetBitmap> e <xref:System.Windows.Media.Imaging.PngBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="3ae12-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae12-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ae12-104">Example</span></span>  
 <span data-ttu-id="3ae12-105"><xref:System.Windows.Media.DrawingVisual>Viene creato utilizzando un oggetto <xref:System.Windows.Media.Imaging.BitmapImage> e <xref:System.Windows.Media.FormattedText> di cui viene eseguito il rendering in un oggetto <xref:System.Windows.Media.Imaging.RenderTargetBitmap> .</span><span class="sxs-lookup"><span data-stu-id="3ae12-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="3ae12-106">La bitmap sottoposta a rendering viene quindi utilizzata per creare un oggetto <xref:System.Windows.Media.Imaging.BitmapFrame> che viene aggiunto a <xref:System.Windows.Media.Imaging.PngBitmapEncoder> per creare un nuovo file di Portable Network Graphics (png).</span><span class="sxs-lookup"><span data-stu-id="3ae12-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="3ae12-107"><xref:System.Windows.Media.Imaging.PngBitmapEncoder>In questo esempio è stato usato un oggetto, ma è possibile che uno qualsiasi degli oggetti derivati <xref:System.Windows.Media.Imaging.BitmapEncoder> sia stato usato per creare il file di immagine.</span><span class="sxs-lookup"><span data-stu-id="3ae12-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae12-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ae12-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="3ae12-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="3ae12-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="3ae12-110">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="3ae12-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="3ae12-111">Utilizzo degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="3ae12-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
