---
title: 'Procedura: modificare la terminazione alla fine di una linea o di un segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969871"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedura: modificare la terminazione alla fine di una linea o di un segmento
Questo esempio illustra come modificare la forma all'inizio o alla fine di un elemento aperto <xref:System.Windows.Shapes.Shape> . Per modificare la terminazione all'inizio di un oggetto aperto <xref:System.Windows.Shapes.Shape> , utilizzare la relativa <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Proprietà. Per modificare la terminazione alla fine di un oggetto aperto <xref:System.Windows.Shapes.Shape> , utilizzare la relativa <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Proprietà. Per visualizzare i limiti di riga disponibili, vedere l' <xref:System.Windows.Media.PenLineCap> enumerazione.  
  
> [!NOTE]
> Questa proprietà ha effetto solo su una forma aperta, ad esempio un oggetto <xref:System.Windows.Shapes.Line> , un oggetto <xref:System.Windows.Shapes.Polyline> o un <xref:System.Windows.Shapes.Path> elemento aperto.  
  
 Nell'esempio seguente vengono disegnati quattro <xref:System.Windows.Shapes.Polyline> elementi e viene utilizzato un set di forme diverso alle estremità di ogni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
