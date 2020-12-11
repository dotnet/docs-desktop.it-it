---
title: 'Procedura: ridimensionare le righe con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966157"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Procedura: ridimensionare le righe con un GridSplitter
Questo esempio illustra come usare un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> per ridistribuire lo spazio tra due righe in un oggetto <xref:System.Windows.Controls.Grid> senza modificare le dimensioni di <xref:System.Windows.Controls.Grid> .  
  
## <a name="example"></a>Esempio  
 **Come creare un oggetto GridSplitter si sovrapponga al bordo di una riga**  
  
 Per specificare un oggetto <xref:System.Windows.Controls.GridSplitter> che ridimensiona le righe adiacenti in un oggetto <xref:System.Windows.Controls.Grid> , impostare la <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata su una delle righe che si desidera ridimensionare. Se il <xref:System.Windows.Controls.Grid> dispone di più di una colonna, impostare la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata per specificare il numero di colonne. Impostare quindi <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.VerticalAlignment.Top> <xref:System.Windows.VerticalAlignment.Bottom> su o (l'allineamento impostato dipende dalle due righe che si desidera ridimensionare). Infine, impostare la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà su <xref:System.Windows.HorizontalAlignment.Stretch> .  
  
 Nell'esempio seguente viene illustrato come definire un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> che ridimensiona le righe adiacenti.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Un oggetto <xref:System.Windows.Controls.GridSplitter> che non occupa una propria riga può essere nascosto da altri controlli in <xref:System.Windows.Controls.Grid> . Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Come creare un oggetto GridSplitter che occupa una riga**  
  
 Per specificare un oggetto <xref:System.Windows.Controls.GridSplitter> che occupa una riga in un oggetto <xref:System.Windows.Controls.Grid> , impostare la <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata su una delle righe che si desidera ridimensionare. Se il <xref:System.Windows.Controls.Grid> dispone di più di una colonna, impostare la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata sul numero di colonne. Impostare quindi <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> su <xref:System.Windows.VerticalAlignment.Center> , impostare la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà su <xref:System.Windows.HorizontalAlignment.Stretch> e impostare la proprietà <xref:System.Windows.Controls.RowDefinition.Height%2A> della riga che contiene l'oggetto <xref:System.Windows.Controls.GridSplitter> su <xref:System.Windows.GridLength.Auto%2A> .  
  
 Nell'esempio seguente viene illustrato come definire un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> che occupa una riga e ridimensiona le righe su entrambi i lati.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridSplitter>
- [Procedure](gridsplitter-how-to-topics.md)
