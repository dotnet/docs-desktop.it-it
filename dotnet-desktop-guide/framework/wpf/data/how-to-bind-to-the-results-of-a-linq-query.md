---
title: "Procedura: eseguire l'associazione ai risultati di una query LINQ"
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 47f39319f2d6a6c67361157afaceb6d605ce01d1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951870"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="f7654-102">Procedura: eseguire l'associazione ai risultati di una query LINQ</span><span class="sxs-lookup"><span data-stu-id="f7654-102">How to: Bind to the Results of a LINQ Query</span></span>

<span data-ttu-id="f7654-103">Questo esempio illustra come eseguire una query LINQ e quindi associarla ai risultati.</span><span class="sxs-lookup"><span data-stu-id="f7654-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>

## <a name="example"></a><span data-ttu-id="f7654-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7654-104">Example</span></span>

<span data-ttu-id="f7654-105">Nell'esempio seguente vengono create due caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f7654-105">The following example creates two list boxes.</span></span> <span data-ttu-id="f7654-106">La prima casella di riepilogo contiene tre elementi elenco.</span><span class="sxs-lookup"><span data-stu-id="f7654-106">The first list box contains three list items.</span></span>

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

<span data-ttu-id="f7654-107">Se si seleziona un elemento dalla prima casella di riepilogo, viene richiamato il gestore eventi seguente.</span><span class="sxs-lookup"><span data-stu-id="f7654-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="f7654-108">In questo esempio, `Tasks` è una raccolta di `Task` oggetti.</span><span class="sxs-lookup"><span data-stu-id="f7654-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="f7654-109">La `Task` classe dispone di una proprietà denominata `Priority` .</span><span class="sxs-lookup"><span data-stu-id="f7654-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="f7654-110">Questo gestore dell'evento esegue una query LINQ che restituisce la raccolta di `Task` oggetti che hanno il valore di priorità selezionato e quindi lo imposta come <xref:System.Windows.FrameworkElement.DataContext%2A> :</span><span class="sxs-lookup"><span data-stu-id="f7654-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

<span data-ttu-id="f7654-111">La seconda casella di riepilogo viene associata a tale raccolta perché il relativo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valore è impostato su `{Binding}` .</span><span class="sxs-lookup"><span data-stu-id="f7654-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="f7654-112">Di conseguenza, viene visualizzata la raccolta restituita, in base a `myTaskTemplate` <xref:System.Windows.DataTemplate> .</span><span class="sxs-lookup"><span data-stu-id="f7654-112">As a result, it displays the returned collection (based on the `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7654-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7654-113">See also</span></span>

- [<span data-ttu-id="f7654-114">Rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="f7654-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="f7654-115">Associa a una raccolta e visualizza le informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="f7654-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="f7654-116">Novità di WPF versione 4.5</span><span class="sxs-lookup"><span data-stu-id="f7654-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="f7654-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="f7654-117">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
