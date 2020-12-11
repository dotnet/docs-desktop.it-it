---
title: 'Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951876"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView
Questo esempio illustra come usare gli <xref:System.Windows.DataTemplate> oggetti e <xref:System.Windows.Style> per specificare l'aspetto di un <xref:System.Windows.Controls.ListView> controllo che usa una <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati gli <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> oggetti e che personalizzano l'aspetto di un'intestazione di colonna per un oggetto <xref:System.Windows.Controls.GridViewColumn> .  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Nell'esempio seguente viene illustrato come utilizzare questi <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> oggetti e per impostare le <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> proprietà e di un oggetto <xref:System.Windows.Controls.GridViewColumn> . La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà definisce il contenuto delle celle della colonna.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>E <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sono solo due delle diverse proprietà che è possibile usare per personalizzare l'aspetto dell'intestazione di colonna per un <xref:System.Windows.Controls.GridView> controllo. Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](gridview-column-header-styles-and-templates-overview.md).  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.DataTemplate> che consente di personalizzare l'aspetto delle celle in un oggetto <xref:System.Windows.Controls.GridViewColumn> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 Nell'esempio seguente viene illustrato come utilizzare questo oggetto <xref:System.Windows.DataTemplate> per definire il contenuto di una <xref:System.Windows.Controls.GridViewColumn> cella. Questo modello viene usato al posto della <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Proprietà mostrata nell' <xref:System.Windows.Controls.GridViewColumn> esempio precedente.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Cenni preliminari su GridView](gridview-overview.md)
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
