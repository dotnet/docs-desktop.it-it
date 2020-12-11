---
title: 'Procedura: implementare un oggetto PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 694679183f92c9737bbdb511b4ebd5a4bf2185f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969703"
---
# <a name="how-to-implement-prioritybinding"></a>Procedura: implementare un oggetto PriorityBinding

<xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Works specificando un elenco di associazioni. L'elenco delle associazioni viene ordinato dalla priorità più alta alla priorità più bassa. Se l'associazione con la priorità più alta restituisce un valore correttamente quando viene elaborato, non è mai necessario elaborare le altre associazioni nell'elenco. Il caso in cui il binding con priorità più elevata impiega molto tempo per la valutazione, la successiva priorità più alta che restituisce un valore verrà utilizzata correttamente finché un'associazione di una priorità più alta non restituirà correttamente un valore.  
  
## <a name="example"></a>Esempio  

 Per illustrare <xref:System.Windows.Data.PriorityBinding> il funzionamento di, l' `AsyncDataSource` oggetto è stato creato con le tre proprietà seguenti: `FastDP` , `SlowerDP` e `SlowestDP` .  
  
 La funzione di accesso get di `FastDP` restituisce il valore del `_fastDP` membro dati.  
  
 La funzione di accesso get di `SlowerDP` attende 3 secondi prima di restituire il valore del `_slowerDP` membro dati.  
  
 La funzione di accesso get di `SlowestDP` attende 5 secondi prima di restituire il valore del `_slowestDP` membro dati.  
  
> [!NOTE]
> Questo esempio viene fornito solo per scopi dimostrativi. Le linee guida di .NET sconsigliano di definire proprietà che sono più lente rispetto a un set di campi. Per ulteriori informazioni, vedere [scelta tra proprietà e metodi](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà viene associata all'oggetto precedente `AsyncDS` utilizzando <xref:System.Windows.Data.PriorityBinding> :  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Quando il motore di binding elabora gli <xref:System.Windows.Data.Binding> oggetti, inizia con il primo <xref:System.Windows.Data.Binding> , associato alla `SlowestDP` Proprietà. Quando <xref:System.Windows.Data.Binding> viene elaborato, il valore non viene restituito correttamente perché è in sospensione per 5 secondi, quindi l' <xref:System.Windows.Data.Binding> elemento successivo viene elaborato. Il successivo <xref:System.Windows.Data.Binding> non restituisce correttamente un valore perché è in sospensione per 3 secondi. Il motore di associazione viene quindi spostato sull' <xref:System.Windows.Data.Binding> elemento successivo, associato alla `FastDP` Proprietà. Viene <xref:System.Windows.Data.Binding> restituito il valore "Fast Value". <xref:System.Windows.Controls.TextBlock>Ora viene visualizzato il valore "valore rapido".  
  
 Dopo 3 secondi trascorsi, la `SlowerDP` proprietà restituisce il valore "valore più lento". <xref:System.Windows.Controls.TextBlock>Viene quindi visualizzato il valore "valore più lento".  
  
 Dopo 5 secondi trascorsi, la `SlowestDP` proprietà restituisce il valore "valore più lento". Tale associazione ha la priorità più alta perché è elencata per prima. <xref:System.Windows.Controls.TextBlock>Viene ora visualizzato il valore "valore più lento".  
  
 <xref:System.Windows.Data.PriorityBinding>Per informazioni su ciò che viene considerato un valore restituito correttamente da un'associazione, vedere.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
