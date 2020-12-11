---
title: 'Procedura: creare ListViewItem con un CheckBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968641"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Procedura: creare ListViewItem con un CheckBox
Questo esempio Mostra come visualizzare una colonna di <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView> controllo che usa un oggetto <xref:System.Windows.Controls.GridView> .  
  
## <a name="example"></a>Esempio  
 Per creare una colonna contenente i <xref:System.Windows.Controls.CheckBox> controlli in un oggetto <xref:System.Windows.Controls.ListView> , creare un oggetto contenente <xref:System.Windows.DataTemplate> un oggetto <xref:System.Windows.Controls.CheckBox> . Impostare quindi <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> <xref:System.Windows.Controls.GridViewColumn> su <xref:System.Windows.DataTemplate> .  
  
 Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.DataTemplate> che contiene un oggetto <xref:System.Windows.Controls.CheckBox> . Nell'esempio viene associata la <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà dell'oggetto <xref:System.Windows.Controls.CheckBox> al <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valore della proprietà dell'oggetto <xref:System.Windows.Controls.ListViewItem> che lo contiene. Pertanto, quando l'oggetto <xref:System.Windows.Controls.ListViewItem> che contiene <xref:System.Windows.Controls.CheckBox> è selezionato, <xref:System.Windows.Controls.CheckBox> viene controllato.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 Nell'esempio seguente viene illustrato come creare una colonna di <xref:System.Windows.Controls.CheckBox> controlli. Per creare la colonna, nell'esempio viene impostata la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà di <xref:System.Windows.Controls.GridViewColumn> su <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Panoramica sul controllo ListView](listview-overview.md)
- [Procedure](listview-how-to-topics.md)
- [Cenni preliminari su GridView](gridview-overview.md)
