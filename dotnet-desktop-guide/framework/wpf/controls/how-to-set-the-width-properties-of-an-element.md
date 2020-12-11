---
title: 'Procedura: impostare le proprietà di larghezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: fcdb8d58c17137d22edd4ee8cf6768c5d7def7c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960877"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Procedura: impostare le proprietà di larghezza di un elemento
## <a name="example"></a>Esempio  
 Questo esempio mostra visivamente le differenze nel comportamento di rendering tra le quattro proprietà correlate alla larghezza in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] .  
  
 La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche di larghezza di un elemento. Queste quattro proprietà possono entrare in conflitto e, quando lo fanno, il valore che ha la precedenza viene determinato nel modo seguente: il valore ha la <xref:System.Windows.FrameworkElement.MinWidth%2A> precedenza sul <xref:System.Windows.FrameworkElement.MaxWidth%2A> valore, che a sua volta ha la precedenza sul valore <xref:System.Windows.FrameworkElement.Width%2A> . Una quarta proprietà, <xref:System.Windows.FrameworkElement.ActualWidth%2A> , è di sola lettura e indica la larghezza effettiva determinata dalle interazioni con il processo di layout.  
  
 Negli esempi seguenti viene [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] disegnato un <xref:System.Windows.Shapes.Rectangle> elemento ( `rect1` ) come figlio di <xref:System.Windows.Controls.Canvas> . È possibile modificare le proprietà di larghezza di un oggetto <xref:System.Windows.Shapes.Rectangle> utilizzando una serie di <xref:System.Windows.Controls.ListBox> elementi che rappresentano i valori delle proprietà di <xref:System.Windows.FrameworkElement.MinWidth%2A> , <xref:System.Windows.FrameworkElement.MaxWidth%2A> e <xref:System.Windows.FrameworkElement.Width%2A> . In questo modo, la precedenza di ogni proprietà viene visualizzata visivamente.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Gli esempi code-behind seguenti gestiscono gli eventi generati dall' <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento. Ogni metodo personalizzato accetta l'input da <xref:System.Windows.Controls.ListBox> , analizza il valore come <xref:System.Double> e applica il valore alla proprietà relativa alla larghezza specificata. I valori di larghezza vengono inoltre convertiti in una stringa e scritti in vari <xref:System.Windows.Controls.TextBlock> elementi (la definizione di tali elementi non viene visualizzata nel codice XAML selezionato).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Per l'esempio completo, vedere [esempio di confronto delle proprietà Width](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Impostare le proprietà di altezza di un elemento](how-to-set-the-height-properties-of-an-element.md)
- [Esempio di confronto delle proprietà Width](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
