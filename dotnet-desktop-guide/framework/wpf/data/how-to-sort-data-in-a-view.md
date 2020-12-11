---
title: 'Procedura: ordinare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 4ff90cc58cb3d7ceee0be2fd7f6ddaaa27df4cef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967075"
---
# <a name="how-to-sort-data-in-a-view"></a>Procedura: ordinare i dati in una visualizzazione
In questo esempio viene descritto come ordinare i dati in una visualizzazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati un semplice <xref:System.Windows.Controls.ListBox> e un <xref:System.Windows.Controls.Button> :  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi del pulsante contiene la logica per ordinare gli elementi in <xref:System.Windows.Controls.ListBox> in ordine decrescente. Questa operazione può essere eseguita perché l'aggiunta di elementi a un oggetto in <xref:System.Windows.Controls.ListBox> questo modo li aggiunge a <xref:System.Windows.Controls.ItemCollection> del <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.ItemCollection> deriva dalla <xref:System.Windows.Data.CollectionView> classe. Se si associa <xref:System.Windows.Controls.ListBox> a una raccolta usando la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà, è possibile usare la stessa tecnica per l'ordinamento.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Purché si disponga di un riferimento all'oggetto View, è possibile utilizzare la stessa tecnica per ordinare il contenuto di altre visualizzazioni di raccolta. Per un esempio di come ottenere una visualizzazione, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md). Per un altro esempio, vedere [ordinare una colonna GridView quando si fa clic su un'intestazione](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Per ulteriori informazioni sulle visualizzazioni, vedere associazione alle raccolte in [Cenni preliminari sul data binding](/dotnet/desktop-wpf/data/data-binding-overview).  
  
 Per un esempio di come applicare la logica di ordinamento in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] , vedere [ordinare e raggruppare dati tramite una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Ordinare una colonna GridView quando si fa clic su un'intestazione](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md)
- [Procedure](data-binding-how-to-topics.md)
