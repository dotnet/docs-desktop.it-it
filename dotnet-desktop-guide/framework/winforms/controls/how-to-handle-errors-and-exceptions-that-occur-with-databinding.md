---
title: 'Procedura: Gestire errori ed eccezioni relativi al data binding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 14326d793be3ee71022a7a1e7398b9af469aab10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961789"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>Procedura: Gestire errori ed eccezioni relativi al data binding
Spesso si verificano eccezioni ed errori negli oggetti business sottostanti quando li si associa ai controlli. È possibile intercettare questi errori ed eccezioni e quindi eseguire il ripristino o passare le informazioni sull'errore all'utente gestendo l'evento <xref:System.Windows.Forms.Binding.BindingComplete> per un determinato componente <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> o <xref:System.Windows.Forms.CurrencyManager>.  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice illustra come gestire gli errori e le eccezioni che si verificano durante un'operazione di data binding. Spiega come intercettare gli errori gestendo l'evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> dell'oggetto <xref:System.Windows.Forms.Binding>. Per intercettare errori ed eccezioni gestendo questo evento, è necessario abilitare la formattazione per l'associazione. È possibile abilitare la formattazione quando il binding viene costruito o aggiunto alla raccolta di binding oppure impostando la proprietà <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> su `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Quando il codice è in esecuzione e viene immessa una stringa vuota come nome parte o un valore inferiore a 100 come codice, appare una finestra di messaggio. Si tratta di un risultato della gestione dell'evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> per questi binding di caselle di testo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [Componente BindingSource](bindingsource-component.md)
