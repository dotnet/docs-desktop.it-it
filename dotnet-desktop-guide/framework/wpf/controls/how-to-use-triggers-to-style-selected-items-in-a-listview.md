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
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="76b0b-102">Procedura: utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="76b0b-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="76b0b-103">In questo esempio viene illustrato come definire <xref:System.Windows.Style.Triggers%2A> per un <xref:System.Windows.Controls.ListViewItem> controllo in modo che, quando il valore di una proprietà di un oggetto <xref:System.Windows.Controls.ListViewItem> cambia, dell'oggetto <xref:System.Windows.Style> delle <xref:System.Windows.Controls.ListViewItem> modifiche in risposta.</span><span class="sxs-lookup"><span data-stu-id="76b0b-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76b0b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="76b0b-104">Example</span></span>  
 <span data-ttu-id="76b0b-105">Se si desidera <xref:System.Windows.Style> modificare la proprietà di un oggetto <xref:System.Windows.Controls.ListViewItem> in risposta alle modifiche delle proprietà, definire <xref:System.Windows.Style.Triggers%2A> per la <xref:System.Windows.Style> modifica.</span><span class="sxs-lookup"><span data-stu-id="76b0b-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="76b0b-106">Nell'esempio seguente viene definito un oggetto <xref:System.Windows.Trigger> che imposta la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà su <xref:System.Windows.Media.Brushes.Blue%2A> e modifica <xref:System.Windows.FrameworkElement.Cursor%2A> per visualizzare un oggetto <xref:System.Windows.Input.CursorType.Hand> quando la <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà viene modificata in `true` .</span><span class="sxs-lookup"><span data-stu-id="76b0b-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="76b0b-107">Nell'esempio seguente viene definito un <xref:System.Windows.MultiTrigger> oggetto che imposta la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.ListViewItem> su <xref:System.Windows.Media.Brushes.Yellow%2A> quando <xref:System.Windows.Controls.ListViewItem> è l'elemento selezionato e con lo stato attivo della tastiera.</span><span class="sxs-lookup"><span data-stu-id="76b0b-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="76b0b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76b0b-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="76b0b-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="76b0b-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="76b0b-110">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="76b0b-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="76b0b-111">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="76b0b-111">GridView Overview</span></span>](gridview-overview.md)
