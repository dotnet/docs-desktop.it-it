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
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati
Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dell'ordinamento, del filtro o del raggruppamento. Le visualizzazioni forniscono anche un concetto di puntatore di record corrente e consentono di trasferire il puntatore. Questo esempio Mostra come ottenere l'oggetto corrente e spostarsi tra gli oggetti in una raccolta di dati usando la funzionalità fornita nella <xref:System.Windows.Data.CollectionView> classe.  
  
## <a name="example"></a>Esempio  
 In questo esempio, `myCollectionView` è un <xref:System.Windows.Data.CollectionView> oggetto che rappresenta una visualizzazione su una raccolta associata.  
  
 Nell'esempio seguente, `OnButton` è un gestore eventi per i `Previous` pulsanti e `Next` in un'applicazione, che sono pulsanti che consentono all'utente di spostarsi nella raccolta dei dati. Si noti che <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> le <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> proprietà e indicano se il puntatore di record corrente è arrivato rispettivamente all'inizio e alla fine dell'elenco, in modo che <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> e <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> possano essere chiamati come appropriato.  
  
 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>Viene eseguito il cast della proprietà della visualizzazione come oggetto `Order` per restituire l'elemento dell'ordine corrente nella raccolta.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md)
- [Filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md)
- [Ordinare e raggruppare dati tramite una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure](data-binding-how-to-topics.md)
