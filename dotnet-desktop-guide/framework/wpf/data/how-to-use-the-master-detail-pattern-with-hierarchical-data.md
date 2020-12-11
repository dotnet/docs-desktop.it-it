---
title: 'Procedura: utilizzare il modello Master-Details con dati gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: dd3ecff2593c88505a1d301f14fe3456e8e4dc85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964552"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="8504a-102">Procedura: utilizzare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="8504a-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="8504a-103">Questo esempio illustra come implementare lo scenario Master-Details.</span><span class="sxs-lookup"><span data-stu-id="8504a-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8504a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8504a-104">Example</span></span>  
 <span data-ttu-id="8504a-105">In questo esempio, `LeagueList` è una raccolta di `Leagues` .</span><span class="sxs-lookup"><span data-stu-id="8504a-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="8504a-106">Ogni `League` ha un `Name` e una raccolta di `Divisions` , ognuno dei `Division` quali ha un nome e una raccolta di `Teams` .</span><span class="sxs-lookup"><span data-stu-id="8504a-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="8504a-107">Ogni `Team` ha un nome del team.</span><span class="sxs-lookup"><span data-stu-id="8504a-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="8504a-108">Lo screenshot seguente mostra l'esempio.</span><span class="sxs-lookup"><span data-stu-id="8504a-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="8504a-109">Il `Divisions` <xref:System.Windows.Controls.ListBox> rileva automaticamente le selezioni in `Leagues` <xref:System.Windows.Controls.ListBox> e Visualizza i dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8504a-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="8504a-110">`Teams` <xref:System.Windows.Controls.ListBox> Rileva le selezioni negli altri due <xref:System.Windows.Controls.ListBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="8504a-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Screenshot che mostra un esempio di scenario di&#45;dettaglio.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="8504a-112">I due aspetti da notare in questo esempio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8504a-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="8504a-113">I tre <xref:System.Windows.Controls.ListBox> controlli vengono associati alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="8504a-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="8504a-114">È possibile impostare la <xref:System.Windows.Data.Binding.Path%2A> proprietà dell'associazione per specificare il livello di dati che si desidera <xref:System.Windows.Controls.ListBox> visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8504a-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="8504a-115">È necessario impostare la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` su sui <xref:System.Windows.Controls.ListBox> controlli di cui si sta verificando la selezione.</span><span class="sxs-lookup"><span data-stu-id="8504a-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="8504a-116">L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="8504a-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="8504a-117">In alternativa, se <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource> , sincronizza automaticamente la selezione e la valuta.</span><span class="sxs-lookup"><span data-stu-id="8504a-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="8504a-118">La tecnica è leggermente diversa quando si utilizzano dati XML.</span><span class="sxs-lookup"><span data-stu-id="8504a-118">The technique is slightly different when you are using XML data.</span></span> <span data-ttu-id="8504a-119">Per un esempio, vedere [usare il modello di Master-Detail con i dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="8504a-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8504a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8504a-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="8504a-121">Associa a una raccolta e visualizza le informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="8504a-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="8504a-122">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="8504a-122">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8504a-123">Cenni preliminari sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="8504a-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="8504a-124">Procedure</span><span class="sxs-lookup"><span data-stu-id="8504a-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
