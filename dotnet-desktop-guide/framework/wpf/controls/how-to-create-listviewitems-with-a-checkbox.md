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
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="bee33-102">Procedura: creare ListViewItem con un CheckBox</span><span class="sxs-lookup"><span data-stu-id="bee33-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="bee33-103">Questo esempio Mostra come visualizzare una colonna di <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView> controllo che usa un oggetto <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="bee33-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bee33-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bee33-104">Example</span></span>  
 <span data-ttu-id="bee33-105">Per creare una colonna contenente i <xref:System.Windows.Controls.CheckBox> controlli in un oggetto <xref:System.Windows.Controls.ListView> , creare un oggetto contenente <xref:System.Windows.DataTemplate> un oggetto <xref:System.Windows.Controls.CheckBox> .</span><span class="sxs-lookup"><span data-stu-id="bee33-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="bee33-106">Impostare quindi <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> <xref:System.Windows.Controls.GridViewColumn> su <xref:System.Windows.DataTemplate> .</span><span class="sxs-lookup"><span data-stu-id="bee33-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="bee33-107">Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.DataTemplate> che contiene un oggetto <xref:System.Windows.Controls.CheckBox> .</span><span class="sxs-lookup"><span data-stu-id="bee33-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="bee33-108">Nell'esempio viene associata la <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà dell'oggetto <xref:System.Windows.Controls.CheckBox> al <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valore della proprietà dell'oggetto <xref:System.Windows.Controls.ListViewItem> che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="bee33-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="bee33-109">Pertanto, quando l'oggetto <xref:System.Windows.Controls.ListViewItem> che contiene <xref:System.Windows.Controls.CheckBox> è selezionato, <xref:System.Windows.Controls.CheckBox> viene controllato.</span><span class="sxs-lookup"><span data-stu-id="bee33-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="bee33-110">Nell'esempio seguente viene illustrato come creare una colonna di <xref:System.Windows.Controls.CheckBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="bee33-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="bee33-111">Per creare la colonna, nell'esempio viene impostata la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà di <xref:System.Windows.Controls.GridViewColumn> su <xref:System.Windows.DataTemplate> .</span><span class="sxs-lookup"><span data-stu-id="bee33-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="bee33-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bee33-112">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="bee33-113">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="bee33-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="bee33-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="bee33-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="bee33-115">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="bee33-115">GridView Overview</span></span>](gridview-overview.md)
