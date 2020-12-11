---
title: 'Procedura: cancellare associazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: ab89c185d1b45ab49e680135ca4c1d54395fe0f4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966634"
---
# <a name="how-to-clear-bindings"></a>Procedura: cancellare associazioni
Questo esempio illustra come cancellare le associazioni da un oggetto.  
  
## <a name="example"></a>Esempio  
 Per cancellare un'associazione da una singola proprietà in un oggetto, chiamare <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> come illustrato nell'esempio seguente. Nell'esempio seguente viene rimossa l'associazione dall' <xref:System.Windows.Controls.TextBlock.TextProperty> oggetto di *testo*, un <xref:System.Windows.Controls.TextBlock> oggetto.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 La cancellazione rimuove l'associazione in modo che il valore della proprietà di dipendenza venga modificato in quello avrebbe assunto senza l'associazione. Questo valore potrebbe essere un valore predefinito, un valore ereditato o un valore ottenuto da un'associazione di modelli di dati.  
  
 Per cancellare i binding da tutte le possibili proprietà di un oggetto, usare <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.BindingOperations>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
