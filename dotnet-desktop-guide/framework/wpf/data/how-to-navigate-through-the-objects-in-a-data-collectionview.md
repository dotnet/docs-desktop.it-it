---
title: 'Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: dc8b1e0dec0f99c3537587fe60cbecf165047f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962773"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="b38cc-102">Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="b38cc-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="b38cc-103">Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dell'ordinamento, del filtro o del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="b38cc-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="b38cc-104">Le visualizzazioni forniscono anche un concetto di puntatore di record corrente e consentono di trasferire il puntatore.</span><span class="sxs-lookup"><span data-stu-id="b38cc-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="b38cc-105">Questo esempio Mostra come ottenere l'oggetto corrente e spostarsi tra gli oggetti in una raccolta di dati usando la funzionalità fornita nella <xref:System.Windows.Data.CollectionView> classe.</span><span class="sxs-lookup"><span data-stu-id="b38cc-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b38cc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b38cc-106">Example</span></span>  
 <span data-ttu-id="b38cc-107">In questo esempio, `myCollectionView` è un <xref:System.Windows.Data.CollectionView> oggetto che rappresenta una visualizzazione su una raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="b38cc-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="b38cc-108">Nell'esempio seguente, `OnButton` è un gestore eventi per i `Previous` pulsanti e `Next` in un'applicazione, che sono pulsanti che consentono all'utente di spostarsi nella raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="b38cc-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="b38cc-109">Si noti che <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> le <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> proprietà e indicano se il puntatore di record corrente è arrivato rispettivamente all'inizio e alla fine dell'elenco, in modo che <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> e <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> possano essere chiamati come appropriato.</span><span class="sxs-lookup"><span data-stu-id="b38cc-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="b38cc-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A>Viene eseguito il cast della proprietà della visualizzazione come oggetto `Order` per restituire l'elemento dell'ordine corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="b38cc-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="b38cc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b38cc-111">See also</span></span>

- [<span data-ttu-id="b38cc-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b38cc-112">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b38cc-113">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b38cc-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="b38cc-114">Filtrare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b38cc-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="b38cc-115">Ordinare e raggruppare dati tramite una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="b38cc-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="b38cc-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="b38cc-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
