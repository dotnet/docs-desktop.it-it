---
title: 'Procedura: utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966322"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Procedura: utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView
In questo esempio viene illustrato come definire <xref:System.Windows.Style.Triggers%2A> per un <xref:System.Windows.Controls.ListViewItem> controllo in modo che, quando il valore di una proprietà di un oggetto <xref:System.Windows.Controls.ListViewItem> cambia, dell'oggetto <xref:System.Windows.Style> delle <xref:System.Windows.Controls.ListViewItem> modifiche in risposta.  
  
## <a name="example"></a>Esempio  
 Se si desidera <xref:System.Windows.Style> modificare la proprietà di un oggetto <xref:System.Windows.Controls.ListViewItem> in risposta alle modifiche delle proprietà, definire <xref:System.Windows.Style.Triggers%2A> per la <xref:System.Windows.Style> modifica.  
  
 Nell'esempio seguente viene definito un oggetto <xref:System.Windows.Trigger> che imposta la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà su <xref:System.Windows.Media.Brushes.Blue%2A> e modifica <xref:System.Windows.FrameworkElement.Cursor%2A> per visualizzare un oggetto <xref:System.Windows.Input.CursorType.Hand> quando la <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà viene modificata in `true` .  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 Nell'esempio seguente viene definito un <xref:System.Windows.MultiTrigger> oggetto che imposta la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.ListViewItem> su <xref:System.Windows.Media.Brushes.Yellow%2A> quando <xref:System.Windows.Controls.ListViewItem> è l'elemento selezionato e con lo stato attivo della tastiera.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
