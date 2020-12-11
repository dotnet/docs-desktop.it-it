---
title: 'Procedura: implementare un oggetto CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: fe3b7fb1020ac8022113246453d8247ca241449c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969715"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="b78a6-102">Procedura: implementare un oggetto CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="b78a6-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="b78a6-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="b78a6-103">Example</span></span>  
 <span data-ttu-id="b78a6-104">Nell'esempio seguente viene illustrato come visualizzare più raccolte ed elementi come un elenco usando la <xref:System.Windows.Data.CompositeCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="b78a6-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="b78a6-105">In questo esempio, `GreekGods` è un oggetto <xref:System.Collections.ObjectModel.ObservableCollection%601> di `GreekGod` oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b78a6-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="b78a6-106">I modelli di dati vengono definiti `GreekGod` in modo che gli oggetti e `GreekHero` gli oggetti vengano visualizzati rispettivamente con un colore di primo piano oro e ciano.</span><span class="sxs-lookup"><span data-stu-id="b78a6-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b78a6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b78a6-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="b78a6-108">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b78a6-108">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b78a6-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="b78a6-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
