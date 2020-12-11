---
title: 'Procedura: utilizzare un disegno come origine di immagini'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961267"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="69cae-102">Procedura: utilizzare un disegno come origine di immagini</span><span class="sxs-lookup"><span data-stu-id="69cae-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="69cae-103">Questo esempio illustra come usare <xref:System.Windows.Media.Drawing> come <xref:System.Windows.Controls.Image.Source%2A> per un <xref:System.Windows.Controls.Image> controllo.</span><span class="sxs-lookup"><span data-stu-id="69cae-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="69cae-104">Per visualizzare un <xref:System.Windows.Media.Drawing> oggetto con un <xref:System.Windows.Controls.Image> controllo, usare un <xref:System.Windows.Media.DrawingImage> oggetto come oggetto del <xref:System.Windows.Controls.Image> controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare la <xref:System.Windows.Media.DrawingImage> proprietà dell'oggetto sul <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> disegno che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="69cae-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69cae-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="69cae-105">Example</span></span>  
 <span data-ttu-id="69cae-106">Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Media.DrawingImage> e un <xref:System.Windows.Controls.Image> controllo per visualizzare un oggetto <xref:System.Windows.Media.GeometryDrawing> .</span><span class="sxs-lookup"><span data-stu-id="69cae-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="69cae-107">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="69cae-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="69cae-108">![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="69cae-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="69cae-109">Oggetto DrawingImage</span><span class="sxs-lookup"><span data-stu-id="69cae-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="69cae-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69cae-110">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="69cae-111">Disegnare un'immagine con ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="69cae-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="69cae-112">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="69cae-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="69cae-113">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="69cae-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="69cae-114">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="69cae-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
