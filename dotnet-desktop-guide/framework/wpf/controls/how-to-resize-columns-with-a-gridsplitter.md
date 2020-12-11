---
title: 'Procedura: ridimensionare le colonne con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966163"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Procedura: ridimensionare le colonne con un GridSplitter
In questo esempio viene illustrato come creare un oggetto verticale per <xref:System.Windows.Controls.GridSplitter> ridistribuire lo spazio tra due colonne in un oggetto <xref:System.Windows.Controls.Grid> senza modificare le dimensioni di <xref:System.Windows.Controls.Grid> .  
  
## <a name="example"></a>Esempio  
 **Come creare un oggetto GridSplitter che si sovrapponga al bordo di una colonna**  
  
 Per specificare un oggetto <xref:System.Windows.Controls.GridSplitter> che ridimensiona le colonne adiacenti in un oggetto <xref:System.Windows.Controls.Grid> , impostare la <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata su una delle colonne che si desidera ridimensionare. Se il <xref:System.Windows.Controls.Grid> dispone di più di una riga, impostare la <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata sul numero di righe. Impostare quindi la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà su <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (l'allineamento impostato dipende dalle due colonne che si desidera ridimensionare). Infine, impostare la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà su <xref:System.Windows.VerticalAlignment.Stretch> .  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Un oggetto <xref:System.Windows.Controls.GridSplitter> che non ha una propria colonna può essere nascosto da altri controlli in <xref:System.Windows.Controls.Grid> . Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Come creare un oggetto GridSplitter che occupa una colonna**  
  
 Per specificare un oggetto <xref:System.Windows.Controls.GridSplitter> che occupa una colonna in un oggetto <xref:System.Windows.Controls.Grid> , impostare la <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata su una delle colonne che si desidera ridimensionare. Se la griglia ha più di una riga, impostare la <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata sul numero di righe. Impostare quindi <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> su <xref:System.Windows.HorizontalAlignment.Center> , impostare la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà su <xref:System.Windows.VerticalAlignment.Stretch> e impostare la proprietà <xref:System.Windows.Controls.ColumnDefinition.Width%2A> della colonna contenente il <xref:System.Windows.Controls.GridSplitter> su <xref:System.Windows.GridLength.Auto%2A> .  
  
 Nell'esempio seguente viene illustrato come definire una verticale <xref:System.Windows.Controls.GridSplitter> che occupa una colonna e ridimensiona le colonne su entrambi i lati.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridSplitter>
- [Procedure](gridsplitter-how-to-topics.md)
