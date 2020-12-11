---
title: 'Procedura: ottenere la visualizzazione predefinita di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 17ec2a40bf2c274f50b39875a23541932438a317
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969721"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Procedura: ottenere la visualizzazione predefinita di una raccolta dati
Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dei criteri di ordinamento, di filtro o di raggruppamento. Ogni raccolta dispone di una visualizzazione predefinita condivisa, che viene utilizzata come origine di associazione effettiva quando un'associazione specifica una raccolta come origine. Questo esempio illustra come ottenere la visualizzazione predefinita di una raccolta.  
  
## <a name="example"></a>Esempio  
 Per creare la vista, è necessario un riferimento a un oggetto alla raccolta. È possibile ottenere questo oggetto dati facendo riferimento al proprio oggetto code-behind, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati o ottenendo una proprietà dell'associazione. In questo esempio viene illustrato come ottenere l' <xref:System.Windows.FrameworkElement.DataContext%2A> oggetto di un oggetto dati e utilizzarlo per ottenere direttamente la visualizzazione di raccolta predefinita per questa raccolta.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel> . <xref:System.Windows.FrameworkElement.DataContext%2A>È impostato su *DataSource*, che fa riferimento a un provider <xref:System.Collections.ObjectModel.ObservableCollection%601> di dati costituito da oggetti *Order* .  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 In alternativa, è possibile creare un'istanza di e associarla alla propria visualizzazione di raccolta usando la <xref:System.Windows.Data.CollectionViewSource> classe. Questa vista di raccolta è condivisa solo dai controlli che lo associano direttamente. Per un esempio, vedere la sezione come creare una vista nella panoramica sul [Data Binding](/dotnet/desktop-wpf/data/data-binding-overview).  
  
 Per esempi della funzionalità fornita da una visualizzazione di raccolta, vedere [ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md), [filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md)e [spostarsi tra gli oggetti in una](how-to-navigate-through-the-objects-in-a-data-collectionview.md)raccolta di dati.  
  
## <a name="see-also"></a>Vedere anche

- [Ordinare e raggruppare dati tramite una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure](data-binding-how-to-topics.md)
