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
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Procedura: utilizzare il modello Master-Details con dati gerarchici
Questo esempio illustra come implementare lo scenario Master-Details.  
  
## <a name="example"></a>Esempio  
 In questo esempio, `LeagueList` è una raccolta di `Leagues` . Ogni `League` ha un `Name` e una raccolta di `Divisions` , ognuno dei `Division` quali ha un nome e una raccolta di `Teams` . Ogni `Team` ha un nome del team.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Lo screenshot seguente mostra l'esempio. Il `Divisions` <xref:System.Windows.Controls.ListBox> rileva automaticamente le selezioni in `Leagues` <xref:System.Windows.Controls.ListBox> e Visualizza i dati corrispondenti. `Teams` <xref:System.Windows.Controls.ListBox> Rileva le selezioni negli altri due <xref:System.Windows.Controls.ListBox> controlli.  
  
 ![Screenshot che mostra un esempio di scenario di&#45;dettaglio.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 I due aspetti da notare in questo esempio sono i seguenti:  
  
1. I tre <xref:System.Windows.Controls.ListBox> controlli vengono associati alla stessa origine. È possibile impostare la <xref:System.Windows.Data.Binding.Path%2A> proprietà dell'associazione per specificare il livello di dati che si desidera <xref:System.Windows.Controls.ListBox> visualizzare.  
  
2. È necessario impostare la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` su sui <xref:System.Windows.Controls.ListBox> controlli di cui si sta verificando la selezione. L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> . In alternativa, se <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource> , sincronizza automaticamente la selezione e la valuta.  
  
 La tecnica è leggermente diversa quando si utilizzano dati XML. Per un esempio, vedere [usare il modello di Master-Detail con i dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.HierarchicalDataTemplate>
- [Associa a una raccolta e visualizza le informazioni in base alla selezione](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Cenni preliminari sui modelli di dati](data-templating-overview.md)
- [Procedure](data-binding-how-to-topics.md)
