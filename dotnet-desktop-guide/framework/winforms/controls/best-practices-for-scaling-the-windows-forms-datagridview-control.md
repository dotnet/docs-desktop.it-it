---
title: Procedure consigliate per il ridimensionamento del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962983"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedure consigliate per ridimensionare il controllo DataGridView Windows Form

Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per garantire la massima scalabilità. Se è necessario visualizzare grandi quantità di dati, attenersi alle linee guida descritte in questo argomento per evitare l'utilizzo di grandi quantità di memoria o la riduzione della velocità di risposta dell'interfaccia utente (UI). In questo argomento vengono illustrati i problemi seguenti:

- Uso efficiente degli stili delle celle

- Utilizzo efficiente di menu di scelta rapida

- Uso efficiente del ridimensionamento automatico

- Utilizzo efficiente delle raccolte celle, righe e colonne selezionate

- Uso di righe condivise

- Impedire la condivisione delle righe

Se si hanno esigenze di prestazioni particolari, è possibile implementare la modalità virtuale e fornire le proprie operazioni di gestione dei dati. Per altre informazioni, vedere [modalità di visualizzazione dati nel controllo DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).

## <a name="using-cell-styles-efficiently"></a>Uso efficiente degli stili delle celle

Ogni cella, riga e colonna può avere le proprie informazioni di stile. Le informazioni sullo stile vengono archiviate in <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti. La creazione di oggetti stile cella per molti singoli <xref:System.Windows.Forms.DataGridView> elementi può risultare inefficiente, soprattutto quando si lavora con grandi quantità di dati. Per evitare un effetto sulle prestazioni, attenersi alle linee guida seguenti:

- Evitare di impostare le proprietà di stile di cella per singoli <xref:System.Windows.Forms.DataGridViewCell> <xref:System.Windows.Forms.DataGridViewRow> oggetti o. Include l'oggetto riga specificato dalla <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Proprietà. Ogni nuova riga clonata dal modello di riga riceverà la propria copia dell'oggetto stile della cella del modello. Per la massima scalabilità, impostare le proprietà di stile della cella al <xref:System.Windows.Forms.DataGridView> livello. Ad esempio, impostare la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà anziché la <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Proprietà.

- Se per alcune celle è necessaria una formattazione diversa da quella predefinita, utilizzare la stessa <xref:System.Windows.Forms.DataGridViewCellStyle> istanza in gruppi di celle, righe o colonne. Evitare di impostare direttamente le proprietà di tipo <xref:System.Windows.Forms.DataGridViewCellStyle> su singole celle, righe e colonne. Per un esempio di condivisione dello stile della cella, vedere [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). È anche possibile evitare una riduzione delle prestazioni quando si impostano gli stili delle celle singolarmente gestendo il <xref:System.Windows.Forms.DataGridView.CellFormatting> gestore eventi. Per un esempio, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).

- Quando si determina lo stile di una cella, utilizzare la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> proprietà anziché la <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Proprietà. <xref:System.Windows.Forms.DataGridViewCell.Style%2A>Se si accede alla proprietà, viene creata una nuova istanza della <xref:System.Windows.Forms.DataGridViewCellStyle> classe se la proprietà non è già stata utilizzata. Inoltre, questo oggetto potrebbe non contenere le informazioni di stile complete per la cella se alcuni stili vengono ereditati dalla riga, dalla colonna o dal controllo. Per ulteriori informazioni sull'ereditarietà dello stile della cella, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="using-shortcut-menus-efficiently"></a>Utilizzo efficiente di menu di scelta rapida

Ogni cella, riga e colonna può avere un proprio menu di scelta rapida. I menu di scelta rapida nel <xref:System.Windows.Forms.DataGridView> controllo sono rappresentati da <xref:System.Windows.Forms.ContextMenuStrip> controlli. Così come per gli oggetti di stile cella, la creazione di menu di scelta rapida per molti singoli <xref:System.Windows.Forms.DataGridView> elementi avrà un impatto negativo sulle prestazioni. Per evitare questi rigore, attenersi alle linee guida seguenti:

- Evitare di creare menu di scelta rapida per singole celle e righe. Questo include il modello di riga, che viene clonato insieme al relativo menu di scelta rapida quando vengono aggiunte nuove righe al controllo. Per la massima scalabilità, utilizzare solo la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà del controllo per specificare un singolo menu di scelta rapida per l'intero controllo.

- Se sono necessari più menu di scelta rapida per più righe o celle, gestire gli <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> eventi o. Questi eventi consentono di gestire gli oggetti del menu di scelta rapida, consentendo di ottimizzare le prestazioni.

## <a name="using-automatic-resizing-efficiently"></a>Uso efficiente del ridimensionamento automatico

Le righe, le colonne e le intestazioni possono essere ridimensionate automaticamente come modifiche al contenuto della cella, in modo che l'intero contenuto delle celle venga visualizzato senza ritaglio. La modifica delle modalità di ridimensionamento può inoltre ridimensionare righe, colonne e intestazioni. Per determinare la dimensione corretta, il <xref:System.Windows.Forms.DataGridView> controllo deve esaminare il valore di ogni cella che deve contenere. Quando si utilizzano set di dati di grandi dimensioni, questa analisi può influire negativamente sulle prestazioni del controllo quando si verifica il ridimensionamento automatico. Per evitare le penalizzazioni delle prestazioni, attenersi alle linee guida seguenti:

- Evitare di usare il ridimensionamento automatico in un <xref:System.Windows.Forms.DataGridView> controllo con un set di righe di grandi dimensioni. Se si usa il ridimensionamento automatico, è sufficiente ridimensionare in base alle righe visualizzate. Usare anche solo le righe visualizzate in modalità virtuale.

  - Per righe e colonne, utilizzare il `DisplayedCells` `DisplayedCellsExceptHeaders` campo o delle <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode> <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> enumerazioni, e <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> .

  - Per le intestazioni di riga, usare il <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> campo o dell' <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> enumerazione.

- Per la massima scalabilità, disattivare il ridimensionamento automatico e usare il ridimensionamento a livello di codice.

Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Utilizzo efficiente delle raccolte celle, righe e colonne selezionate

La <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> raccolta non viene eseguita in modo efficiente con selezioni di grandi dimensioni. Le <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> raccolte e possono anche essere inefficienti, anche se a un livello inferiore perché sono presenti molte meno righe rispetto alle celle di un <xref:System.Windows.Forms.DataGridView> controllo tipico e molte meno colonne rispetto alle righe. Per evitare le penalizzazioni delle prestazioni durante l'utilizzo di queste raccolte, attenersi alle linee guida seguenti:

- Per determinare se tutte le celle di <xref:System.Windows.Forms.DataGridView> sono state selezionate prima di accedere al contenuto della <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> raccolta, controllare il valore restituito del <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metodo. Si noti, tuttavia, che questo metodo può impedire la condivisione delle righe. Per ulteriori informazioni, vedere la sezione successiva.

- Evitare di utilizzare la <xref:System.Collections.ICollection.Count%2A> proprietà di <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> per determinare il numero di celle selezionate. Usare invece il <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> metodo e passare il <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> valore. Analogamente, utilizzare <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> i <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> metodi e per determinare il numero di elementi selezionati, anziché accedere alle raccolte di righe e colonne selezionate.

- Evitare le modalità di selezione basate su celle. In alternativa, impostare la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> .

## <a name="using-shared-rows"></a>Uso di righe condivise

Un utilizzo efficiente della memoria viene effettuato nel <xref:System.Windows.Forms.DataGridView> controllo tramite righe condivise. Le righe condividono quante più informazioni sul loro aspetto e comportamento possibile condividendo le istanze della <xref:System.Windows.Forms.DataGridViewRow> classe.

Durante la condivisione di istanze di riga viene salvata la memoria, le righe possono essere facilmente non condivise. Ad esempio, ogni volta che un utente interagisce direttamente con una cella, viene annullata la condivisione della relativa riga. Poiché questa operazione non può essere evitata, le linee guida in questo argomento sono utili solo quando si lavora con grandi quantità di dati e solo quando gli utenti interagiranno con una parte relativamente piccola dei dati ogni volta che viene eseguito il programma.

Una riga non può essere condivisa in un controllo non associato <xref:System.Windows.Forms.DataGridView> se una delle relative celle contiene valori. Quando il <xref:System.Windows.Forms.DataGridView> controllo è associato a un'origine dati esterna o quando si implementa la modalità virtuale e si fornisce un'origine dati personalizzata, i valori delle celle vengono archiviati all'esterno del controllo anziché negli oggetti cella, consentendo la condivisione delle righe.

Un oggetto riga può essere condiviso solo se lo stato di tutte le relative celle può essere determinato dallo stato della riga e dagli Stati delle colonne contenenti le celle. Se si modifica lo stato di una cella in modo che non possa più essere dedotto dallo stato della relativa riga e colonna, la riga non può essere condivisa.

Una riga, ad esempio, non può essere condivisa in una delle situazioni seguenti:

- La riga contiene una sola cella selezionata che non si trova in una colonna selezionata.

- La riga contiene una cella con le <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> relative <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> proprietà o impostate.

- La riga contiene un oggetto <xref:System.Windows.Forms.DataGridViewComboBoxCell> con il relativo <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> set di proprietà.

In modalità associata o in modalità virtuale è possibile fornire descrizioni comandi e menu di scelta rapida per le singole celle gestendo gli <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> eventi e.

Il <xref:System.Windows.Forms.DataGridView> controllo tenterà automaticamente di utilizzare righe condivise ogni volta che vengono aggiunte righe a <xref:System.Windows.Forms.DataGridViewRowCollection> . Usare le linee guida seguenti per assicurarsi che le righe siano condivise:

- Evitare di chiamare l' `Add(Object[])` Overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo e l' `Insert(Object[])` Overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo della <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta. Questi overload creano automaticamente righe non condivise.

- Assicurarsi che la riga specificata nella <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà possa essere condivisa nei casi seguenti:

  - Quando si chiamano `Add()` gli `Add(Int32)` Overload o del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo o l' `Insert(Int32,Int32)` Overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo della <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta.

  - Quando si aumenta il valore della <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> Proprietà.

  - Quando si imposta la <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> Proprietà.

- Assicurarsi che la riga indicata dal `indexSource` parametro possa essere condivisa quando si chiamano i <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> metodi, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A> , <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> e <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> della <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta.

- Assicurarsi che la riga o le righe specificate possano essere condivise quando si chiama l' `Add(DataGridViewRow)` Overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo, il <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> metodo, l' `Insert(Int32,DataGridViewRow)` Overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo e il <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> metodo della <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta.

Per determinare se una riga è condivisa, utilizzare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> metodo per recuperare l'oggetto riga, quindi controllare la proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewBand.Index%2A> . Il <xref:System.Windows.Forms.DataGridViewBand.Index%2A> valore della proprietà delle righe condivise è sempre-1.

## <a name="preventing-rows-from-becoming-unshared"></a>Impedire la condivisione delle righe

È possibile annullare la condivisione delle righe condivise in seguito all'azione del codice o dell'utente. Per evitare un effetto sulle prestazioni, è consigliabile evitare che le righe vengano non condivise. Durante lo sviluppo di applicazioni, è possibile gestire l' <xref:System.Windows.Forms.DataGridView.RowUnshared> evento per determinare quando le righe diventano non condivise. Questa operazione è utile durante il debug dei problemi di condivisione delle righe.

Per impedire che le righe diventino non condivise, attenersi alle linee guida seguenti:

- Evitare l'indicizzazione della <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta o l'iterazione tramite un `foreach` ciclo. In genere non è necessario accedere direttamente alle righe. <xref:System.Windows.Forms.DataGridView> i metodi che operano sulle righe accettano argomenti di indice di riga anziché istanze di riga. Inoltre, i gestori per gli eventi correlati alla riga ricevono oggetti argomento dell'evento con proprietà di riga che è possibile usare per modificare le righe senza comportarne la condivisione.

- Se è necessario accedere a un oggetto riga, usare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> metodo e passare l'indice effettivo della riga. Si noti, tuttavia, che la modifica di un oggetto riga condiviso recuperato tramite questo metodo modificherà tutte le righe che condividono questo oggetto. La riga per i nuovi record non è tuttavia condivisa con altre righe, pertanto non sarà interessata quando si modifica un'altra riga. Si noti inoltre che diverse righe rappresentate da una riga condivisa possono avere diversi menu di scelta rapida. Per recuperare il menu di scelta rapida corretto da un'istanza di riga condivisa, usare il <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> metodo e passare l'indice effettivo della riga. Se invece si accede alla proprietà della riga condivisa <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> , verrà utilizzato l'indice di riga condiviso di-1 e non verrà recuperato il menu di scelta rapida corretto.

- Evitare l'indicizzazione della <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> raccolta. Se si accede direttamente a una cella, viene annullata la condivisione della riga padre, creando un'istanza di un nuovo oggetto <xref:System.Windows.Forms.DataGridViewRow> . I gestori per gli eventi correlati alle celle ricevono oggetti argomento dell'evento con proprietà delle celle che è possibile usare per modificare le celle senza causare la condivisione delle righe. È anche possibile usare la <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> proprietà per recuperare gli indici di riga e di colonna della cella corrente senza accedere direttamente alla cella.

- Evitare le modalità di selezione basate su celle. Queste modalità comportano la non condivisione delle righe. In alternativa, impostare la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> .

- Non gestire gli <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> eventi o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> . Questi eventi impediscono la condivisione delle righe. Inoltre, non chiamare i <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> metodi o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> , che generano questi eventi.

- Non accedere alla <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> raccolta quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> , <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> , <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> . In questo modo verrà annullata la condivisione di tutte le righe selezionate.

- Non chiamare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> metodo. Questo metodo può impedire la condivisione delle righe.

- Non chiamare il <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> metodo quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> . In questo modo verrà annullata la condivisione di tutte le righe.

- Non impostare la <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> proprietà o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> di una cella su `false` quando la proprietà corrispondente nella relativa colonna è impostata su `true` . In questo modo verrà annullata la condivisione di tutte le righe.

- Non accedere alla <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> Proprietà. In questo modo verrà annullata la condivisione di tutte le righe.

- Non chiamare l' `Sort(IComparer)` Overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo. L'ordinamento con un operatore di confronto personalizzato causa la non condivisione di tutte le righe.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
