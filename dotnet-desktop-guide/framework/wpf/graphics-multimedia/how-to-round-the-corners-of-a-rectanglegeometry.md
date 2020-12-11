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
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Procedura: arrotondare gli angoli di un oggetto RectangleGeometry
Per arrotondare gli angoli di un oggetto <xref:System.Windows.Media.RectangleGeometry> , impostarne le <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà e su un valore maggiore di zero. Maggiore è il numero di valori, arrotondare gli angoli del rettangolo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrati diversi <xref:System.Windows.Media.RectangleGeometry> oggetti con diverse <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Impostazioni e. Gli <xref:System.Windows.Media.RectangleGeometry> oggetti vengono visualizzati utilizzando <xref:System.Windows.Shapes.Path> gli elementi.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rettangoli con impostazioni RadiusX&#47;RadiusY diverse](./media/graphicsmm-rounded.png "graphicsmm_rounded")  
Rettangoli con angoli arrotondati  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
