---
title: 'Procedura: creare un oggetto GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967981"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="09fcb-102">Procedura: creare un oggetto GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="09fcb-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="09fcb-103">Questo esempio illustra come creare e visualizzare un oggetto <xref:System.Windows.Media.GeometryDrawing> .</span><span class="sxs-lookup"><span data-stu-id="09fcb-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="09fcb-104">Un oggetto <xref:System.Windows.Media.GeometryDrawing> consente di creare una forma con un riempimento e un contorno associando un oggetto <xref:System.Windows.Media.Pen> e un oggetto a un oggetto <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Geometry> .</span><span class="sxs-lookup"><span data-stu-id="09fcb-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="09fcb-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A>Descrive la struttura della forma, <xref:System.Windows.Media.GeometryDrawing.Brush%2A> che descrive il riempimento della forma e <xref:System.Windows.Media.GeometryDrawing.Pen%2A> descrive il contorno della forma.</span><span class="sxs-lookup"><span data-stu-id="09fcb-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09fcb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="09fcb-106">Example</span></span>  
 <span data-ttu-id="09fcb-107">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.GeometryDrawing> per eseguire il rendering di una forma.</span><span class="sxs-lookup"><span data-stu-id="09fcb-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="09fcb-108">La forma è descritta da un oggetto <xref:System.Windows.Media.GeometryGroup> e da due <xref:System.Windows.Media.EllipseGeometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="09fcb-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="09fcb-109">L'interno della forma viene disegnato con un oggetto <xref:System.Windows.Media.LinearGradientBrush> e il contorno viene disegnato con un oggetto <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> .</span><span class="sxs-lookup"><span data-stu-id="09fcb-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="09fcb-110"><xref:System.Windows.Media.GeometryDrawing>Viene visualizzato utilizzando un oggetto <xref:System.Windows.Media.ImageDrawing> e un <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="09fcb-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="09fcb-111">La figura seguente mostra l'oggetto risultante <xref:System.Windows.Media.GeometryDrawing> .</span><span class="sxs-lookup"><span data-stu-id="09fcb-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="09fcb-112">![Oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="09fcb-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="09fcb-113">Per creare disegni più complessi, è possibile combinare più oggetti Drawing in un singolo disegno composto usando un oggetto <xref:System.Windows.Media.DrawingGroup> .</span><span class="sxs-lookup"><span data-stu-id="09fcb-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fcb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09fcb-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="09fcb-115">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="09fcb-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="09fcb-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="09fcb-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="09fcb-117">Creare un disegno composto</span><span class="sxs-lookup"><span data-stu-id="09fcb-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
