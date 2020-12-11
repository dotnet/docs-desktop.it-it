---
title: 'Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8a39c50bfc452c807a18a9bf0a65e56cb75d20aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951322"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati
Spesso quando si utilizzano data binding in Windows Forms, più controlli vengono associati alla stessa origine dati. In alcuni casi, potrebbe essere necessario eseguire passaggi aggiuntivi per assicurarsi che le proprietà associate dei controlli rimangano sincronizzate tra loro e l'origine dati. Questi passaggi sono necessari in due situazioni:  
  
- Se l'origine dati non implementa <xref:System.ComponentModel.IBindingList> e pertanto genera <xref:System.ComponentModel.IBindingList.ListChanged> eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> .  
  
- Se l'origine dati implementa <xref:System.ComponentModel.IEditableObject> .  
  
 Nel primo caso, è possibile usare un oggetto <xref:System.Windows.Forms.BindingSource> per associare l'origine dati ai controlli. Nel secondo caso, si usa un oggetto <xref:System.Windows.Forms.BindingSource> e si gestisce l' <xref:System.Windows.Forms.BindingSource.BindingComplete> evento e si chiama nell'oggetto <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> associato <xref:System.Windows.Forms.BindingManagerBase> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come associare tre controlli, due controlli casella di testo e un <xref:System.Windows.Forms.DataGridView> controllo, alla stessa colonna in un oggetto <xref:System.Data.DataSet> utilizzando un <xref:System.Windows.Forms.BindingSource> componente. In questo esempio viene illustrato come gestire l' <xref:System.Windows.Forms.BindingSource.BindingComplete> evento e assicurarsi che quando viene modificato il valore di testo di una casella di testo, la casella di testo aggiuntiva e il <xref:System.Windows.Forms.DataGridView> controllo vengono aggiornati con il valore corretto.  
  
 Nell'esempio viene utilizzato un oggetto <xref:System.Windows.Forms.BindingSource> per associare l'origine dati e i controlli. In alternativa, è possibile associare i controlli direttamente all'origine dati e recuperare <xref:System.Windows.Forms.BindingManagerBase> per l'associazione dal form, <xref:System.Windows.Forms.Control.BindingContext%2A> quindi gestire l' <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> evento per <xref:System.Windows.Forms.BindingManagerBase> . Per un esempio di come eseguire questa operazione, vedere la pagina della Guida relativa all' <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> evento di <xref:System.Windows.Forms.BindingManagerBase> .  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Questo esempio di codice richiede  
  
- Riferimenti agli assembly <xref:System>, <xref:System.Windows.Forms> e <xref:System.Drawing>.  
  
- Un form con l' <xref:System.Windows.Forms.Form.Load> evento gestito e una chiamata al `InitializeControlsAndDataSource` metodo nell'esempio dal <xref:System.Windows.Forms.Form.Load> gestore eventi del form.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Condividere i dati associati tra moduli usando il componente BindingSource](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [Notifica delle modifiche nell'associazione dati dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Interfacce correlate al data binding](interfaces-related-to-data-binding.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)
