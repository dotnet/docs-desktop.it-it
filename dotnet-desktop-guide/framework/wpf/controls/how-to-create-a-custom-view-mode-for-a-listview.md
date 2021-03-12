---
title: 'Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 6c6c8475849354493330105e93316d6424ebe2f3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604277"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="9a1ee-102">Procedura: creare una modalità di visualizzazione personalizzata per un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9a1ee-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="9a1ee-103">Questo esempio illustra come creare una modalità personalizzata <xref:System.Windows.Controls.ListView.View%2A> per un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a1ee-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a1ee-104">Example</span></span>  
 <span data-ttu-id="9a1ee-105">È necessario utilizzare la <xref:System.Windows.Controls.ViewBase> classe quando si crea una visualizzazione personalizzata per il <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="9a1ee-106">Nell'esempio seguente viene illustrata una modalità `PlainView` di visualizzazione denominata derivata dalla <xref:System.Windows.Controls.ViewBase> classe.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="9a1ee-107">Per applicare uno stile alla visualizzazione personalizzata, usare la <xref:System.Windows.Style> classe.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="9a1ee-108">Nell'esempio seguente viene definito un oggetto <xref:System.Windows.Style> per la `PlainView` modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="9a1ee-109">Nell'esempio precedente, questo stile è impostato come valore della <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> proprietà definita per `PlainView` .</span><span class="sxs-lookup"><span data-stu-id="9a1ee-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="9a1ee-110">Per definire il layout dei dati in una modalità di visualizzazione personalizzata, definire un <xref:System.Windows.DataTemplate> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="9a1ee-111">Nell'esempio seguente viene definito un oggetto <xref:System.Windows.DataTemplate> che può essere utilizzato per visualizzare i dati in `PlainView` modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="9a1ee-112">Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.ResourceKey> per la `PlainView` modalità di visualizzazione che utilizza l'oggetto <xref:System.Windows.DataTemplate> definito nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="9a1ee-113">Un <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione personalizzata se si imposta la <xref:System.Windows.Controls.ListView.View%2A> proprietà sulla chiave di risorsa.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="9a1ee-114">Nell'esempio seguente viene illustrato come specificare `PlainView` come modalità di visualizzazione per un oggetto <xref:System.Windows.Controls.ListView> .</span><span class="sxs-lookup"><span data-stu-id="9a1ee-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="9a1ee-115">Per l'esempio completo, vedere [ListView con più visualizzazioni (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con più visualizzazioni (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="9a1ee-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1ee-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9a1ee-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="9a1ee-117">Procedure</span><span class="sxs-lookup"><span data-stu-id="9a1ee-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="9a1ee-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9a1ee-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="9a1ee-119">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="9a1ee-119">GridView Overview</span></span>](gridview-overview.md)
