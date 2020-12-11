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
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Procedura: eseguire l'associazione ai risultati di una query LINQ

Questo esempio illustra come eseguire una query LINQ e quindi associarla ai risultati.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono create due caselle di riepilogo. La prima casella di riepilogo contiene tre elementi elenco.

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

Se si seleziona un elemento dalla prima casella di riepilogo, viene richiamato il gestore eventi seguente. In questo esempio, `Tasks` è una raccolta di `Task` oggetti. La `Task` classe dispone di una proprietà denominata `Priority` . Questo gestore dell'evento esegue una query LINQ che restituisce la raccolta di `Task` oggetti che hanno il valore di priorità selezionato e quindi lo imposta come <xref:System.Windows.FrameworkElement.DataContext%2A> :

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

La seconda casella di riepilogo viene associata a tale raccolta perché il relativo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valore è impostato su `{Binding}` . Di conseguenza, viene visualizzata la raccolta restituita, in base a `myTaskTemplate` <xref:System.Windows.DataTemplate> .

## <a name="see-also"></a>Vedere anche

- [Rendere i dati disponibili per l'associazione in XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Associa a una raccolta e visualizza le informazioni in base alla selezione](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Novità di WPF versione 4.5](../getting-started/whats-new.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
