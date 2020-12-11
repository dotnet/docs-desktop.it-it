---
title: Uso della riga per i nuovi record nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966685"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
Quando si usa un <xref:System.Windows.Forms.DataGridView> per la modifica dei dati nell'applicazione, spesso si vuole offrire agli utenti la possibilità di aggiungere nuove righe di dati all'archivio dati. Il <xref:System.Windows.Forms.DataGridView> controllo supporta questa funzionalità fornendo una riga per i nuovi record, che viene sempre visualizzata come ultima riga. È contrassegnato con un asterisco (*) nell'intestazione di riga. Le sezioni seguenti illustrano alcuni aspetti da considerare quando si programma con la riga per i nuovi record abilitati.  
  
## <a name="displaying-the-row-for-new-records"></a>Visualizzazione della riga per i nuovi record  
 Utilizzare la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà per indicare se la riga per i nuovi record viene visualizzata. Il valore predefinito di questa proprietà è `true`.  
  
 Per il caso di associazione dati, la riga per i nuovi record verrà visualizzata se la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà del controllo e la <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> proprietà dell'origine dati sono entrambe `true` . Se il valore è `false` , la riga non verrà visualizzata.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Popolamento della riga per i nuovi record con dati predefiniti  
 Quando l'utente seleziona la riga per i nuovi record come riga corrente, il <xref:System.Windows.Forms.DataGridView> controllo genera l' <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.  
  
 Questo evento consente di accedere al nuovo <xref:System.Windows.Forms.DataGridViewRow> e consente di popolare la nuova riga con i dati predefiniti. Per altre informazioni, vedere [procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Raccolta Rows  
 La riga per i nuovi record è contenuta nella <xref:System.Windows.Forms.DataGridView> raccolta del controllo <xref:System.Windows.Forms.DataGridView.Rows%2A> , ma si comporta in modo diverso in due aspetti:  
  
- La riga per i nuovi record non può essere rimossa dalla <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta a livello di codice. <xref:System.InvalidOperationException>Viene generata un'eccezione se si tenta di eseguire questa operazione. L'utente non può inoltre eliminare la riga per i nuovi record. Il <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> metodo non rimuove questa riga dalla <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta.  
  
- Non è possibile aggiungere alcuna riga dopo la riga per i nuovi record. Se si tenta di eseguire un'eccezione <xref:System.InvalidOperationException> , viene generata un'eccezione. Di conseguenza, la riga per i nuovi record è sempre l'ultima riga nel <xref:System.Windows.Forms.DataGridView> controllo. I metodi su <xref:System.Windows.Forms.DataGridViewRowCollection> che aggiungono righe <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> ,, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> e, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A> chiamano tutti i metodi di inserimento internamente quando è presente la riga per i nuovi record.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalizzazione visiva della riga per i nuovi record  
 Quando viene creata la riga per i nuovi record, si basa sulla riga specificata dalla <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Proprietà. Gli stili di cella non specificati per questa riga vengono ereditati da altre proprietà. Per ulteriori informazioni sull'ereditarietà dello stile della cella, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 I valori iniziali visualizzati dalle celle della riga per i nuovi record vengono recuperati dalla proprietà di ciascuna cella <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> . Per le celle di tipo <xref:System.Windows.Forms.DataGridViewImageCell> , questa proprietà restituisce un'immagine segnaposto. In caso contrario la proprietà restituisce `null`. È possibile eseguire l'override di questa proprietà per restituire un valore personalizzato. Tuttavia, questi valori iniziali possono essere sostituiti da un <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> gestore eventi quando lo stato attivo immette la riga per i nuovi record.  
  
 Le icone standard per l'intestazione di questa riga, ovvero una freccia o un asterisco, non vengono esposte pubblicamente. Se si desidera personalizzare le icone, sarà necessario creare una <xref:System.Windows.Forms.DataGridViewRowHeaderCell> classe personalizzata.  
  
 Le icone standard utilizzano la <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> proprietà di utilizzata <xref:System.Windows.Forms.DataGridViewCellStyle> dalla cella di intestazione di riga. Non viene eseguito il rendering delle icone standard se lo spazio disponibile non è sufficiente per visualizzarli completamente.  
  
 Se per la cella dell'intestazione di riga è impostato un valore di stringa e lo spazio disponibile non è sufficiente per il testo e l'icona, l'icona viene eliminata per prima.  
  
## <a name="sorting"></a>Ordinamento  
 In modalità non associata, i nuovi record verranno sempre aggiunti alla fine di <xref:System.Windows.Forms.DataGridView> anche se l'utente ha ordinato il contenuto di <xref:System.Windows.Forms.DataGridView> . L'utente dovrà applicare nuovamente l'ordinamento per ordinare la riga nella posizione corretta; Questo comportamento è simile a quello del <xref:System.Windows.Forms.ListView> controllo.  
  
 Nelle modalità di associazione dati e virtuali, il comportamento di inserimento quando viene applicato un ordinamento dipende dall'implementazione del modello di dati. Per ADO.NET, la riga viene immediatamente ordinata nella posizione corretta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Altre note sulla riga per i nuovi record  
 Non è possibile impostare la <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> proprietà di questa riga su `false` . Se si tenta di eseguire un'eccezione <xref:System.InvalidOperationException> , viene generata un'eccezione.  
  
 La riga per i nuovi record viene sempre creata con lo stato deselezionato.  
  
## <a name="virtual-mode"></a>Modalità virtuale  
 Se si implementa la modalità virtuale, sarà necessario tenere traccia del momento in cui è necessaria una riga per i nuovi record nel modello di dati e quando eseguire il rollback dell'aggiunta della riga. L'implementazione esatta di questa funzionalità dipende dall'implementazione del modello di dati e dalla relativa semantica di transazione, ad esempio se l'ambito del commit è a livello di cella o di riga. Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataGridView Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)
