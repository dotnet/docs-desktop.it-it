---
title: 'Procedura: disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951258"
---
# <a name="how-to-draw-a-line"></a>Procedura: disegnare una linea
Questo esempio illustra come creare linee usando l' <xref:System.Windows.Shapes.Line> elemento.  
  
 Per creare una linea, creare un <xref:System.Windows.Shapes.Line> elemento. Usare le <xref:System.Windows.Shapes.Line.X1%2A> <xref:System.Windows.Shapes.Line.Y1%2A> proprietà e per impostarne il punto iniziale e usare le <xref:System.Windows.Shapes.Line.X2%2A> <xref:System.Windows.Shapes.Line.Y2%2A> proprietà e per impostarne il punto finale. Infine, impostare la proprietà <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché una linea priva di un tratto è invisibile.  
  
 L'impostazione dell' <xref:System.Windows.Shapes.Shape.Fill%2A> elemento per una riga non ha alcun effetto, perché una linea non ha interni.  
  
 Nell'esempio seguente vengono disegnate tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Line>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
