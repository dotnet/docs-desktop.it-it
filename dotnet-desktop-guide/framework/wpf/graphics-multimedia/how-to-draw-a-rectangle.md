---
title: 'Procedura: disegnare un rettangolo'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951590"
---
# <a name="how-to-draw-a-rectangle"></a>Procedura: disegnare un rettangolo
Questo esempio illustra come creare un rettangolo usando l' <xref:System.Windows.Shapes.Rectangle> elemento.  
  
 Per creare un rettangolo, creare un <xref:System.Windows.Shapes.Rectangle> elemento e specificare i relativi <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> . Per disegnare l'interno del rettangolo, impostarne il relativo oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> . Per assegnare un contorno al rettangolo, utilizzare <xref:System.Windows.Shapes.Shape.Stroke%2A> le <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà e.  
  
 Per assegnare gli angoli arrotondati al rettangolo, specificare le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> proprietà e facoltative <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> . Le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà e consentono di impostare l'asse x e il raggio dell'asse y dell'ellisse utilizzata per arrotondare gli angoli del rettangolo.  
  
 Nell'esempio seguente <xref:System.Windows.Shapes.Rectangle> vengono disegnati due elementi in un oggetto <xref:System.Windows.Controls.Canvas> . Il primo rettangolo ha una parte <xref:System.Windows.Media.Brushes.Blue%2A> interna. Il secondo rettangolo ha una parte <xref:System.Windows.Media.Brushes.Blue%2A> interna, una <xref:System.Windows.Media.Brushes.Black%2A> struttura e gli angoli arrotondati.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Sebbene in questo esempio venga utilizzato un oggetto <xref:System.Windows.Controls.Canvas> per contenere i rettangoli, è possibile utilizzare gli elementi Rectangle (e tutti gli altri elementi Shape) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporti contenuto non di testo. Infatti, i rettangoli sono particolarmente utili per fornire sfondi per parti di <xref:System.Windows.Controls.Grid> pannelli. Per un esempio, vedere [Panoramica della tabella](../advanced/table-overview.md).  
  
 Questo esempio fa parte di un esempio più ampio; per l'esempio completo, vedere [esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Rectangle>
- [Esempio di elementi Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sull'elemento Table](../advanced/table-overview.md)
