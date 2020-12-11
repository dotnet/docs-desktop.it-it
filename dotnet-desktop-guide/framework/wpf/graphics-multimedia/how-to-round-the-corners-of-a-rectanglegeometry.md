---
title: 'Procedura: arrotondare gli angoli di un oggetto RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966886"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="5c9c3-102">Procedura: arrotondare gli angoli di un oggetto RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="5c9c3-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="5c9c3-103">Per arrotondare gli angoli di un oggetto <xref:System.Windows.Media.RectangleGeometry> , impostarne le <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà e su un valore maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="5c9c3-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="5c9c3-104">Maggiore è il numero di valori, arrotondare gli angoli del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="5c9c3-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c9c3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c9c3-105">Example</span></span>  
 <span data-ttu-id="5c9c3-106">Nell'esempio seguente vengono illustrati diversi <xref:System.Windows.Media.RectangleGeometry> oggetti con diverse <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Impostazioni e.</span><span class="sxs-lookup"><span data-stu-id="5c9c3-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="5c9c3-107">Gli <xref:System.Windows.Media.RectangleGeometry> oggetti vengono visualizzati utilizzando <xref:System.Windows.Shapes.Path> gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5c9c3-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="5c9c3-108">![Rettangoli con impostazioni RadiusX&#47;RadiusY diverse](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="5c9c3-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="5c9c3-109">Rettangoli con angoli arrotondati</span><span class="sxs-lookup"><span data-stu-id="5c9c3-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9c3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c9c3-110">See also</span></span>

- [<span data-ttu-id="5c9c3-111">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="5c9c3-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="5c9c3-112">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="5c9c3-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="5c9c3-113">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="5c9c3-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
