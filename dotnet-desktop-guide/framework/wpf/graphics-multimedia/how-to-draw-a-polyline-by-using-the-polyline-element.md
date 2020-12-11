---
title: "Procedura: disegnare una polilinea utilizzando l'elemento polilinea"
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4871d357d81ec80b63e69e6af133ae10b4e08b15
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969886"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Procedura: disegnare una polilinea utilizzando l'elemento polilinea
Questo esempio illustra come creare una polilinea, ovvero una serie di linee connesse, usando l' <xref:System.Windows.Shapes.Polyline> elemento.  
  
 Per disegnare una polilinea, creare un <xref:System.Windows.Shapes.Polyline> elemento e utilizzare la relativa <xref:System.Windows.Shapes.Polyline.Points%2A> proprietà per specificare i vertici della forma. Usare infine le <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> per descrivere il contorno della polilinea perché una linea priva di tratto è invisibile.  
  
> [!NOTE]
> Poiché l' <xref:System.Windows.Shapes.Polyline> elemento non è una forma chiusa, la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà non ha alcun effetto, neanche se si chiude intenzionalmente il contorno della forma. Per creare una forma chiusa con un oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> , usare un <xref:System.Windows.Shapes.Polygon> elemento.  
  
 Nell'esempio seguente vengono disegnati due <xref:System.Windows.Shapes.Polyline> elementi all'interno di un oggetto <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Sebbene in questo esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere le polilinee, è possibile utilizzare gli elementi polilinea (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
