---
title: Tipi di colonna nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951218"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Tipi di colonna nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo Usa diversi tipi di colonna per visualizzare le informazioni e consentire agli utenti di modificare o aggiungere informazioni.  
  
 Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo e si imposta la <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> proprietà su `true` , le colonne vengono generate automaticamente utilizzando i tipi di colonna predefiniti appropriati per i tipi di dati contenuti nell'origine dati associata.  
  
 È anche possibile creare istanze di qualsiasi classe di colonna e aggiungerle alla raccolta restituita dalla <xref:System.Windows.Forms.DataGridView.Columns%2A> Proprietà. È possibile creare queste istanze da utilizzare come colonne non associate oppure è possibile associarle manualmente. Le colonne associate manualmente sono utili, ad esempio, quando si desidera sostituire una colonna generata automaticamente di un tipo con una colonna di un altro tipo.  
  
 Nella tabella seguente vengono descritte le varie classi di colonna disponibili per l'utilizzo nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Utilizzato con valori basati su testo. Generato automaticamente quando si esegue l'associazione a numeri e stringhe.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Utilizzato con <xref:System.Boolean> <xref:System.Windows.Forms.CheckState> i valori e. Generato automaticamente quando si esegue l'associazione a valori di questi tipi.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Usato per visualizzare immagini. Generato automaticamente quando si esegue l'associazione a matrici di byte, <xref:System.Drawing.Image> oggetti o <xref:System.Drawing.Icon> oggetti.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Utilizzato per visualizzare i pulsanti nelle celle. Non viene generato automaticamente quando si esegue l'associazione. Usato in genere come colonne non vincolate.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Utilizzato per visualizzare gli elenchi a discesa nelle celle. Non viene generato automaticamente quando si esegue l'associazione. Viene in genere associato a dati manualmente.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Utilizzato per visualizzare i collegamenti nelle celle. Non viene generato automaticamente quando si esegue l'associazione. Viene in genere associato a dati manualmente.|  
|Tipo di colonna personalizzato|È possibile creare una classe di colonna personalizzata ereditando la <xref:System.Windows.Forms.DataGridViewColumn> classe o una delle relative classi derivate per fornire un aspetto personalizzato, un comportamento o controlli ospitati. Per altre informazioni, vedere [procedura: personalizzare celle e colonne nel controllo DataGridView Windows Forms estendendo il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Questi tipi di colonna sono descritti in modo più dettagliato nelle sezioni seguenti.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>È un tipo di colonna di uso generico da usare con valori basati su testo quali numeri e stringhe. In modalità di modifica, <xref:System.Windows.Forms.TextBox> viene visualizzato un controllo nella cella attiva, che consente agli utenti di modificare il valore della cella.  
  
 I valori delle celle vengono convertiti automaticamente in stringhe per la visualizzazione. I valori immessi o modificati dall'utente vengono analizzati automaticamente per creare un valore di cella del tipo di dati appropriato. È possibile personalizzare queste conversioni gestendo gli <xref:System.Windows.Forms.DataGridView.CellFormatting> eventi e <xref:System.Windows.Forms.DataGridView.CellParsing> del <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Il tipo di dati del valore della cella di una colonna viene specificato nella <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> proprietà della colonna.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>Viene utilizzato con <xref:System.Boolean> <xref:System.Windows.Forms.CheckState> i valori e. <xref:System.Boolean> i valori vengono visualizzati come caselle di controllo a due Stati o a tre stati, a seconda del valore della <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> Proprietà. Quando la colonna è associata a <xref:System.Windows.Forms.CheckState> valori, il <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> valore della proprietà è `true` per impostazione predefinita.  
  
 In genere, i valori delle celle della casella di controllo sono destinati ad archiviazione, come qualsiasi altro tipo di dati o per l'esecuzione di operazioni bulk. Se si desidera rispondere immediatamente quando gli utenti fanno clic su una cella della casella di controllo, è possibile gestire l' <xref:System.Windows.Forms.DataGridView.CellClick> evento, ma questo evento si verifica prima dell'aggiornamento del valore della cella. Se è necessario il nuovo valore al momento del clic, un'opzione consiste nel calcolare il valore previsto che verrà basato sul valore corrente. Un altro approccio consiste nell'eseguire immediatamente il commit della modifica e gestire l' <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento per rispondervi. Per eseguire il commit della modifica quando si fa clic sulla cella, è necessario gestire l' <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> evento. Nel gestore, se la cella corrente è una cella della casella di controllo, chiamare il <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> metodo e passare il <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> valore.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn>Viene utilizzato per visualizzare le immagini. Le colonne immagine possono essere popolate automaticamente da un'origine dati, popolate manualmente per le colonne non in associazione o popolate dinamicamente in un gestore per l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
 Il popolamento automatico di una colonna immagine da un'origine dati funziona con matrici di byte in diversi formati di immagine, inclusi tutti i formati supportati dalla <xref:System.Drawing.Image> classe e il formato immagine OLE utilizzato da Microsoft® Access e dal database di esempio Northwind.  
  
 Il popolamento manuale di una colonna image è utile quando si desidera fornire la funzionalità di un oggetto <xref:System.Windows.Forms.DataGridViewButtonColumn> , ma con un aspetto personalizzato. È possibile gestire l' <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> evento per rispondere ai clic all'interno di una cella dell'immagine.  
  
 Il popolamento delle celle di una colonna immagine in un gestore per l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento è utile quando si desidera fornire immagini per valori o valori calcolati in formati non di immagine. Ad esempio, è possibile che si disponga di una colonna "Risk" con valori stringa, ad esempio `"high"` , `"middle"` e `"low"` che si desidera visualizzare come icone. In alternativa, è possibile che sia presente una colonna "image" che contiene i percorsi delle immagini che devono essere caricate anziché il contenuto binario delle immagini.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Con <xref:System.Windows.Forms.DataGridViewButtonColumn> , è possibile visualizzare una colonna di celle che contengono pulsanti. Questa operazione è utile quando si desidera fornire agli utenti un modo semplice per eseguire azioni su record specifici, ad esempio l'inserimento di un ordine o la visualizzazione di record figlio in una finestra separata.  
  
 Le colonne dei pulsanti non vengono generate automaticamente quando si associa un controllo ai dati <xref:System.Windows.Forms.DataGridView> . Per usare le colonne dei pulsanti, è necessario crearle manualmente e aggiungerle alla raccolta restituita dalla <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> Proprietà.  
  
 È possibile rispondere ai clic dell'utente nelle celle dei pulsanti gestendo l' <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> evento.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Con <xref:System.Windows.Forms.DataGridViewComboBoxColumn> , è possibile visualizzare una colonna di celle che contengono caselle di riepilogo a discesa. Questa operazione è utile per l'immissione di dati in campi che possono contenere solo valori specifici, ad esempio la colonna Category della tabella Products nel database di esempio Northwind.  
  
 È possibile popolare l'elenco a discesa usato per tutte le celle nello stesso modo in cui si popola un <xref:System.Windows.Forms.ComboBox> elenco a discesa, manualmente tramite la raccolta restituita dalla <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> proprietà o mediante l'associazione a un'origine dati tramite le <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> . Per ulteriori informazioni, vedere [controllo ComboBox](combobox-control-windows-forms.md).  
  
 È possibile associare i valori di cella effettivi all'origine dati utilizzata dal <xref:System.Windows.Forms.DataGridView> controllo impostando la <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> .  
  
 Le colonne della casella combinata non vengono generate automaticamente quando si associa un controllo ai dati <xref:System.Windows.Forms.DataGridView> . Per usare le colonne della casella combinata, è necessario crearle manualmente e aggiungerle alla raccolta restituita dalla <xref:System.Windows.Forms.DataGridView.Columns%2A> Proprietà.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Con <xref:System.Windows.Forms.DataGridViewLinkColumn> , è possibile visualizzare una colonna di celle che contengono collegamenti ipertestuali. Questa operazione è utile per i valori URL nell'origine dati o come alternativa alla colonna Button per comportamenti speciali, ad esempio l'apertura di una finestra con record figlio.  
  
 Le colonne di collegamento non vengono generate automaticamente quando si associa un controllo ai dati <xref:System.Windows.Forms.DataGridView> . Per utilizzare le colonne di collegamento, è necessario crearle manualmente e aggiungerle alla raccolta restituita dalla <xref:System.Windows.Forms.DataGridView.Columns%2A> Proprietà.  
  
 È possibile rispondere ai clic sui collegamenti dell'utente gestendo l' <xref:System.Windows.Forms.DataGridView.CellContentClick> evento. Questo evento è diverso dagli <xref:System.Windows.Forms.DataGridView.CellClick> eventi e <xref:System.Windows.Forms.DataGridView.CellMouseClick> , che si verificano quando un utente fa clic in un punto qualsiasi di una cella.  
  
 La <xref:System.Windows.Forms.DataGridViewLinkColumn> classe fornisce diverse proprietà per modificare l'aspetto dei collegamenti prima, durante e dopo aver fatto clic su di essi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Procedura: Visualizzare immagini nelle celle del controllo DataGridView di Windows Forms](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Procedura: Usare le colonne di immagini nel controllo DataGridView di Windows Forms](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Personalizzazione del controllo DataGridView Windows Form](customizing-the-windows-forms-datagridview-control.md)
