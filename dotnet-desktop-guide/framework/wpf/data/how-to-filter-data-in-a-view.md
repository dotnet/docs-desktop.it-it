---
title: 'Procedura: filtrare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: c015194609de507725a17fbe5d72e41d7027c68f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969733"
---
# <a name="how-to-filter-data-in-a-view"></a>Procedura: filtrare i dati in una visualizzazione
Questo esempio Mostra come filtrare i dati in una visualizzazione.  
  
## <a name="example"></a>Esempio  
 Per creare un filtro, definire un metodo che fornisca la logica di filtro. Il metodo viene utilizzato come callback e accetta un parametro di tipo `object` . Il metodo seguente restituisce tutti gli `Order` oggetti con la `filled` proprietà impostata su "No", filtrando il resto degli oggetti.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 È quindi possibile applicare il filtro, come illustrato nell'esempio seguente. In questo esempio `myCollectionView` è un <xref:System.Windows.Data.ListCollectionView> oggetto.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Per annullare l'applicazione di filtri, è possibile impostare la <xref:System.Windows.Data.CollectionView.Filter%2A> proprietà su `null` :  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Per informazioni su come creare o ottenere una vista, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md). Per l'esempio completo, vedere [ordinamento e filtro degli elementi in un esempio di visualizzazione](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).  
  
 Se l'oggetto visualizzazione deriva da un <xref:System.Windows.Data.CollectionViewSource> oggetto, applicare la logica di filtro impostando un gestore eventi per l' <xref:System.Windows.Data.CollectionViewSource.Filter> evento. Nell'esempio seguente, `listingDataView` è un'istanza di <xref:System.Windows.Data.CollectionViewSource> .  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Di seguito viene illustrata l'implementazione del `ShowOnlyBargainsFilter` gestore eventi di filtro di esempio. Questo gestore eventi usa la <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> proprietà per filtrare `AuctionItem` gli oggetti con un `CurrentPrice` valore di $25 o superiore.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md)
- [Procedure](data-binding-how-to-topics.md)
