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
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="4f806-102">Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView</span><span class="sxs-lookup"><span data-stu-id="4f806-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="4f806-103">Questo esempio illustra come usare gli <xref:System.Windows.DataTemplate> oggetti e <xref:System.Windows.Style> per specificare l'aspetto di un <xref:System.Windows.Controls.ListView> controllo che usa una <xref:System.Windows.Controls.GridView> modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f806-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f806-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f806-104">Example</span></span>  
 <span data-ttu-id="4f806-105">Negli esempi seguenti vengono illustrati gli <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> oggetti e che personalizzano l'aspetto di un'intestazione di colonna per un oggetto <xref:System.Windows.Controls.GridViewColumn> .</span><span class="sxs-lookup"><span data-stu-id="4f806-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="4f806-106">Nell'esempio seguente viene illustrato come utilizzare questi <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> oggetti e per impostare le <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> proprietà e di un oggetto <xref:System.Windows.Controls.GridViewColumn> .</span><span class="sxs-lookup"><span data-stu-id="4f806-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="4f806-107">La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà definisce il contenuto delle celle della colonna.</span><span class="sxs-lookup"><span data-stu-id="4f806-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="4f806-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>E <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sono solo due delle diverse proprietà che è possibile usare per personalizzare l'aspetto dell'intestazione di colonna per un <xref:System.Windows.Controls.GridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="4f806-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="4f806-109">Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f806-109">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="4f806-110">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.DataTemplate> che consente di personalizzare l'aspetto delle celle in un oggetto <xref:System.Windows.Controls.GridViewColumn> .</span><span class="sxs-lookup"><span data-stu-id="4f806-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="4f806-111">Nell'esempio seguente viene illustrato come utilizzare questo oggetto <xref:System.Windows.DataTemplate> per definire il contenuto di una <xref:System.Windows.Controls.GridViewColumn> cella.</span><span class="sxs-lookup"><span data-stu-id="4f806-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="4f806-112">Questo modello viene usato al posto della <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Proprietà mostrata nell' <xref:System.Windows.Controls.GridViewColumn> esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4f806-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="4f806-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f806-113">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="4f806-114">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="4f806-114">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="4f806-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="4f806-115">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="4f806-116">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="4f806-116">ListView Overview</span></span>](listview-overview.md)
