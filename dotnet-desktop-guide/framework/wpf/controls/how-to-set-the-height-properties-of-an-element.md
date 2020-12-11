---
title: 'Procedura: impostare le proprietà di altezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: f18612d66c477562eb387b76ea30e71dd5f4e8d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968917"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Procedura: impostare le proprietà di altezza di un elemento
## <a name="example"></a>Esempio  
 Questo esempio mostra visivamente le differenze nel comportamento di rendering tra le quattro proprietà correlate all'altezza in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] .  
  
 La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche di altezza di un elemento. Queste quattro proprietà possono entrare in conflitto e, quando lo fanno, il valore che ha la precedenza viene determinato nel modo seguente: il valore ha la <xref:System.Windows.FrameworkElement.MinHeight%2A> precedenza sul <xref:System.Windows.FrameworkElement.MaxHeight%2A> valore, che a sua volta ha la precedenza sul valore <xref:System.Windows.FrameworkElement.Height%2A> . Una quarta proprietà, <xref:System.Windows.FrameworkElement.ActualHeight%2A> , è di sola lettura e indica l'altezza effettiva in base a quanto determinato dalle interazioni con il processo di layout.  
  
 Negli esempi seguenti viene [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] disegnato un <xref:System.Windows.Shapes.Rectangle> elemento ( `rect1` ) come figlio di <xref:System.Windows.Controls.Canvas> . È possibile modificare le proprietà di altezza di un oggetto <xref:System.Windows.Shapes.Rectangle> utilizzando una serie di <xref:System.Windows.Controls.ListBox> elementi che rappresentano i valori delle proprietà di <xref:System.Windows.FrameworkElement.MinHeight%2A> , <xref:System.Windows.FrameworkElement.MaxHeight%2A> e <xref:System.Windows.FrameworkElement.Height%2A> . In questo modo, la precedenza di ogni proprietà viene visualizzata visivamente.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Gli esempi code-behind seguenti gestiscono gli eventi generati dall' <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento. Ogni gestore accetta l'input da <xref:System.Windows.Controls.ListBox> , analizza il valore come <xref:System.Double> e applica il valore alla proprietà relativa all'altezza specificata. I valori di altezza vengono inoltre convertiti in una stringa e scritti in vari <xref:System.Windows.Controls.TextBlock> elementi (la definizione di tali elementi non viene visualizzata nel codice XAML selezionato).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Per l'esempio completo, vedere [esempio di proprietà Height](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Impostare le proprietà di larghezza di un elemento](how-to-set-the-width-properties-of-an-element.md)
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Esempio di proprietà Height](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
