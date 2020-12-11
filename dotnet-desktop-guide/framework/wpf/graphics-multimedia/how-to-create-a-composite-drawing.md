---
title: 'Procedura: creare un disegno composto'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970003"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="0c5f5-102">Procedura: creare un disegno composto</span><span class="sxs-lookup"><span data-stu-id="0c5f5-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="0c5f5-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingGroup> per creare disegni complessi combinando più <xref:System.Windows.Media.Drawing> oggetti in un singolo disegno composto.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c5f5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c5f5-104">Example</span></span>  
 <span data-ttu-id="0c5f5-105">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.DrawingGroup> per creare un disegno composto <xref:System.Windows.Media.GeometryDrawing> dagli <xref:System.Windows.Media.ImageDrawing> oggetti e.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="0c5f5-106">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0c5f5-107">![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="0c5f5-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="0c5f5-108">Disegno composito creato tramite l'oggetto DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="0c5f5-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="0c5f5-109">Si noti il bordo grigio, che mostra i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="0c5f5-110">È possibile usare un oggetto <xref:System.Windows.Media.DrawingGroup> per applicare un'impostazione,,, <xref:System.Windows.Media.DrawingGroup.Transform%2A> <xref:System.Windows.Media.DrawingGroup.Opacity%2A> <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> ai disegni che contiene.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="0c5f5-111">Poiché un oggetto <xref:System.Windows.Media.DrawingGroup> è anche un <xref:System.Windows.Media.Drawing> , può contenere altri <xref:System.Windows.Media.DrawingGroup> oggetti.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="0c5f5-112">L'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che usa <xref:System.Windows.Media.DrawingGroup> oggetti aggiuntivi per applicare gli effetti bitmap e una maschera di opacità ad alcuni dei relativi disegni.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="0c5f5-113">L'immagine seguente illustra l'output generato dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0c5f5-114">![Oggetto DrawingGroup con più disegni](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="0c5f5-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="0c5f5-115">Disegno composito con più oggetti DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="0c5f5-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="0c5f5-116">Si noti il bordo grigio, che mostra i limiti del disegno.</span><span class="sxs-lookup"><span data-stu-id="0c5f5-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="0c5f5-117">Per altre informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c5f5-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5f5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5f5-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="0c5f5-119">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="0c5f5-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
