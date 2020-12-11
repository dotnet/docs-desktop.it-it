---
title: 'Procedura: raggruppare gli elementi di un controllo ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961372"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Procedura: raggruppare gli elementi di un controllo ListView che implementa una GridView
Questo esempio Mostra come visualizzare i gruppi di elementi nella <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 Per visualizzare i gruppi di elementi in un oggetto <xref:System.Windows.Controls.ListView> , definire un oggetto <xref:System.Windows.Data.CollectionViewSource> . Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Data.CollectionViewSource> che raggruppa gli elementi di dati in base al valore del `Catalog` campo dati.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 Nell'esempio seguente viene impostato l'oggetto <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per l'oggetto <xref:System.Windows.Controls.ListView> <xref:System.Windows.Data.CollectionViewSource> che viene definito dall'esempio precedente. Nell'esempio viene inoltre definito un oggetto <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> che implementa un <xref:System.Windows.Controls.Expander> controllo.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
