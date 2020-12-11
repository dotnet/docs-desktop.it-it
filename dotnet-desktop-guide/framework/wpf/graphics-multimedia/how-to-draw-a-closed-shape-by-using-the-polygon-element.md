---
title: "Procedura: disegnare una forma chiusa utilizzando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 53359d05555a572796961a82c7b5e95f14ebddc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969889"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Procedura: disegnare una forma chiusa utilizzando l'elemento poligono
In questo esempio viene illustrato come disegnare una forma chiusa utilizzando l' <xref:System.Windows.Shapes.Polygon> elemento. Per disegnare una forma chiusa, creare un <xref:System.Windows.Shapes.Polygon> elemento e utilizzare la relativa <xref:System.Windows.Shapes.Polygon.Points%2A> proprietà per specificare i vertici di una forma. Viene disegnata automaticamente una linea che connette il primo e l'ultimo punto. Infine, specificare, <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> o.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] la sintassi valida per i punti è un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Sebbene nell'esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile utilizzare gli elementi Polygon (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo.  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).
