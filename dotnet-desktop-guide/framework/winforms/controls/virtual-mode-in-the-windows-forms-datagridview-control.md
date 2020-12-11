---
title: Modalità virtuale nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 0d82f0fc9946e5b61ea171f2f5d2ab5690db0c71
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966844"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtuale nel controllo DataGridView di Windows Form
Con la modalità virtuale è possibile gestire l'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e una cache di dati personalizzata. Per implementare la modalità virtuale, impostare la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà su `true` e gestire uno o più eventi descritti in questo argomento. In genere si gestirà almeno l' `CellValueNeeded` evento, che consente al controllo di cercare i valori nella cache dei dati.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modalità associata e modalità virtuale  
 La modalità virtuale è necessaria solo quando è necessario completare o sostituire la modalità di associazione. In modalità di associazione, impostare la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà e il controllo carica automaticamente i dati dall'origine specificata e invia di nuovo le modifiche dell'utente. È possibile controllare quali colonne associate vengono visualizzate e l'origine dati gestisce in genere operazioni quali l'ordinamento.  
  
## <a name="supplementing-bound-mode"></a>Aggiunta della modalità associata  
 È possibile integrare la modalità di associazione visualizzando le colonne non associate insieme alle colonne associate. Questa operazione viene a volte definita "modalità mista" ed è utile per la visualizzazione di elementi come i valori calcolati o i controlli dell'interfaccia utente.  
  
 Poiché le colonne non associate si trovano all'esterno dell'origine dati, vengono ignorate dalle operazioni di ordinamento dell'origine dati. Pertanto, quando si Abilita l'ordinamento in modalità mista, è necessario gestire i dati non associati in una cache locale e implementare la modalità virtuale per consentire al <xref:System.Windows.Forms.DataGridView> controllo di interagire con esso.  
  
 Per ulteriori informazioni sull'utilizzo della modalità virtuale per mantenere i valori nelle colonne non vincolate, vedere gli esempi negli <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> argomenti di riferimento alla proprietà e alla <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> classe.  
  
## <a name="replacing-bound-mode"></a>Sostituzione della modalità associata  
 Se la modalità associata non soddisfa le esigenze di prestazioni, è possibile gestire tutti i dati in una cache personalizzata tramite gestori eventi in modalità virtuale. È ad esempio possibile utilizzare la modalità virtuale per implementare un meccanismo di caricamento dei dati JIT che recupera solo la quantità di dati da un database in rete, come necessario per ottenere prestazioni ottimali. Questo scenario è particolarmente utile quando si lavora con grandi quantità di dati su una connessione di rete lenta o con computer client con una quantità limitata di RAM o spazio di archiviazione.  
  
 Per ulteriori informazioni sull'utilizzo della modalità virtuale in uno scenario JIT, vedere [implementazione della modalità virtuale con caricamento dati JIT nel controllo Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventi Virtual-Mode  
 Se i dati sono di sola lettura, l' `CellValueNeeded` evento può essere l'unico evento che è necessario gestire. Eventi in modalità virtuale aggiuntivi consentono di abilitare funzionalità specifiche come le modifiche dell'utente, l'aggiunta e l'eliminazione di righe e le transazioni a livello di riga.  
  
 Alcuni eventi standard, <xref:System.Windows.Forms.DataGridView> ad esempio gli eventi che si verificano quando gli utenti aggiungono o eliminano righe o quando i valori delle celle vengono modificati, analizzati, convalidati o formattati, sono utili anche in modalità virtuale. È inoltre possibile gestire gli eventi che consentono di gestire i valori che in genere non vengono archiviati in un'origine dati associata, ad esempio testo della descrizione comando per celle, testo di errore della cella e della riga, dati del menu di scelta rapida per celle e righe e dati di altezza delle righe.  
  
 Per ulteriori informazioni sull'implementazione della modalità virtuale per gestire i dati di lettura/scrittura con un ambito di commit a livello di riga, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
 Per un esempio in cui viene implementata la modalità virtuale con un ambito di commit a livello di cella, vedere l' <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> argomento di riferimento della proprietà.  
  
 Gli eventi seguenti si verificano solo quando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà è impostata su `true` .  
  
|Event|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Utilizzato dal controllo per recuperare il valore di una cella dalla cache dei dati per la visualizzazione. Questo evento si verifica solo per le celle nelle colonne non in associazione.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Utilizzato dal controllo per eseguire il commit dell'input utente per una cella nella cache dei dati. Questo evento si verifica solo per le celle nelle colonne non in associazione.<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo quando si modifica un valore memorizzato nella cache all'esterno di un <xref:System.Windows.Forms.DataGridView.CellValuePushed> gestore eventi per garantire che il valore corrente venga visualizzato nel controllo e per applicare le modalità di ridimensionamento automatico attualmente attive.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Utilizzato dal controllo per indicare la necessità di una nuova riga nella cache dei dati.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Utilizzato dal controllo per determinare se una riga contiene modifiche di cui non è stato eseguito il commit.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Utilizzato dal controllo per indicare che una riga deve ripristinare i valori memorizzati nella cache.|  
  
 Gli eventi seguenti sono utili in modalità virtuale, ma possono essere usati indipendentemente dall' <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> impostazione della proprietà.  
  
|Eventi|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Utilizzato dal controllo per indicare quando le righe vengono eliminate o aggiunte, consentendo di aggiornare la cache dei dati di conseguenza.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Utilizzato dal controllo per formattare i valori delle celle per la visualizzazione e per analizzare e convalidare l'input dell'utente.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Utilizzato dal controllo per recuperare il testo della descrizione comando della cella quando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà è `true` .<br /><br /> Le descrizioni comandi della cella vengono visualizzate solo quando il <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> valore della proprietà è `true` .|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Utilizzato dal controllo per recuperare il testo di errore della cella o della riga quando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà è `true` .<br /><br /> Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> metodo o il <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> metodo quando si modifica il testo di errore della cella o della riga per assicurarsi che il valore corrente venga visualizzato nel controllo.<br /><br /> Quando i <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> valori delle proprietà e sono, vengono visualizzate le icone di errore della cella e della riga <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> `true` .|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Utilizzato dal controllo per recuperare una cella o una riga <xref:System.Windows.Forms.ContextMenuStrip> quando la proprietà del controllo <xref:System.Windows.Forms.DataGridView.DataSource%2A> è impostata o la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà è `true` .|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Utilizzato dal controllo per recuperare o archiviare le informazioni sull'altezza della riga nella cache dei dati. Chiamare il <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> metodo quando si modificano le informazioni sull'altezza della riga memorizzata nella cache al di fuori di un <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> gestore eventi per garantire che il valore corrente venga utilizzato nella visualizzazione del controllo.|  
  
## <a name="best-practices-in-virtual-mode"></a>Procedure consigliate in modalità virtuale  
 Se si implementa la modalità virtuale per lavorare in modo efficiente con grandi quantità di dati, è anche necessario assicurarsi che si stia lavorando in modo efficiente con il <xref:System.Windows.Forms.DataGridView> controllo stesso. Per ulteriori informazioni sull'utilizzo efficiente di stili di cella, ridimensionamento automatico, selezioni e condivisione di righe, vedere [procedure consigliate per la scalabilità del controllo Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
