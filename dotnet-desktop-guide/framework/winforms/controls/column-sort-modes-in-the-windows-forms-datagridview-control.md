---
title: Modalità di ordinamento delle colonne nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951219"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form
<xref:System.Windows.Forms.DataGridView> le colonne dispongono di tre modalità di ordinamento. La modalità di ordinamento per ogni colonna viene specificata tramite la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà della colonna, che può essere impostata su uno dei seguenti <xref:System.Windows.Forms.DataGridViewColumnSortMode> valori di enumerazione.  
  
|Valore della proprietà `DataGridViewColumnSortMode`|Descrizione|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Impostazione predefinita per le colonne della casella di testo. A meno che le intestazioni di colonna non vengano utilizzate per la selezione, facendo clic sull'intestazione di colonna viene automaticamente ordinata <xref:System.Windows.Forms.DataGridView> in base a questa colonna e viene visualizzato un glifo che indica l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Impostazione predefinita per le colonne della casella di testo non. È possibile ordinare questa colonna a livello di codice. Tuttavia, non è destinato all'ordinamento, pertanto nessuno spazio viene riservato per il glifo di ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|È possibile ordinare questa colonna a livello di codice e lo spazio è riservato per il glifo di ordinamento.|  
  
 Potrebbe essere necessario modificare la modalità di ordinamento per una colonna per la quale il valore predefinito <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> è se contiene valori che possono essere ordinati in modo significativo. Se, ad esempio, è presente una colonna di database contenente numeri che rappresentano gli Stati degli elementi, è possibile visualizzare questi numeri come icone corrispondenti associando una colonna dell'immagine alla colonna del database. È quindi possibile modificare i valori delle celle numeriche in valori di visualizzazione immagine in un gestore per l' <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. In questo caso, l'impostazione della proprietà su consentirà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> agli utenti di ordinare la colonna. L'ordinamento automatico consentirà agli utenti di raggruppare gli elementi che hanno lo stesso stato anche se gli stati corrispondenti ai numeri non hanno una sequenza naturale. Le colonne della casella di controllo sono un altro esempio in cui l'ordinamento automatico è utile per raggruppare gli elementi nello stesso stato.  
  
 È possibile ordinare un oggetto a <xref:System.Windows.Forms.DataGridView> livello di codice in base ai valori di qualsiasi colonna o in più colonne, indipendentemente dalle <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> impostazioni. L'ordinamento a livello di codice è utile quando si desidera fornire un'interfaccia utente personalizzata per l'ordinamento o quando si desidera implementare l'ordinamento personalizzato. Fornire un'interfaccia utente di ordinamento personalizzata è utile, ad esempio, quando si imposta la <xref:System.Windows.Forms.DataGridView> modalità di selezione per abilitare la selezione dell'intestazione di colonna. In questo caso, anche se le intestazioni di colonna non possono essere utilizzate per l'ordinamento, è comunque necessario che le intestazioni visualizzino il glifo di ordinamento appropriato, quindi impostare la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà su <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic> .  
  
 Le colonne impostate sulla modalità di ordinamento a livello di codice non visualizzano automaticamente un glifo di ordinamento. Per queste colonne, è necessario visualizzare il glifo impostando la <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> Proprietà. Questa operazione è necessaria se si vuole flessibilità nell'ordinamento personalizzato. Se ad esempio si ordina <xref:System.Windows.Forms.DataGridView> in base a più colonne, potrebbe essere necessario visualizzare più glifi di ordinamento o nessun glifo di ordinamento.  
  
 Sebbene sia possibile ordinare a a livello <xref:System.Windows.Forms.DataGridView> di codice un per ogni colonna, alcune colonne, ad esempio le colonne dei pulsanti, potrebbero non contenere valori che possono essere ordinati in modo significativo. Per queste colonne, un' <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> impostazione della proprietà di <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica che non verrà mai utilizzata per l'ordinamento, pertanto non è necessario riservare spazio nell'intestazione per il glifo di ordinamento.  
  
 Quando un oggetto <xref:System.Windows.Forms.DataGridView> è ordinato, è possibile determinare la colonna di ordinamento e l'ordinamento controllando i valori delle <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> proprietà e <xref:System.Windows.Forms.DataGridView.SortOrder%2A> . Questi valori non sono significativi dopo un'operazione di ordinamento personalizzata. Per ulteriori informazioni sull'ordinamento personalizzato, vedere la sezione ordinamento personalizzato più avanti in questo argomento.  
  
 Quando <xref:System.Windows.Forms.DataGridView> viene ordinato un controllo contenente le colonne con binding e non associato, i valori nelle colonne non vincolate non possono essere mantenuti automaticamente. Per mantenere questi valori, è necessario implementare la modalità virtuale impostando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà su `true` e gestendo gli <xref:System.Windows.Forms.DataGridView.CellValueNeeded> <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventi e. Per altre informazioni, vedere [procedura: implementare la modalità virtuale nel controllo DataGridView Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). L'ordinamento in base a colonne non vincolate in modalità di associazione non è supportato.  
  
## <a name="programmatic-sorting"></a>Ordinamento a livello di codice  
 È possibile ordinare un oggetto a <xref:System.Windows.Forms.DataGridView> livello di codice chiamando il relativo <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo.  
  
 L' `Sort(DataGridViewColumn,ListSortDirection)` Overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo accetta un oggetto <xref:System.Windows.Forms.DataGridViewColumn> e un <xref:System.ComponentModel.ListSortDirection> valore di enumerazione come parametri. Questo overload è utile quando si esegue l'ordinamento in base a colonne con valori che possono essere ordinati in modo significativo, ma che non si desidera configurare per l'ordinamento automatico. Quando si chiama questo overload e si passa una colonna con il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valore della proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType> , le <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> <xref:System.Windows.Forms.DataGridView.SortOrder%2A> proprietà e vengono impostate automaticamente e nell'intestazione di colonna viene visualizzato il glifo di ordinamento appropriato.  
  
> [!NOTE]
> Quando il <xref:System.Windows.Forms.DataGridView> controllo è associato a un'origine dati esterna impostando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà, l' `Sort(DataGridViewColumn,ListSortDirection)` Overload del metodo non funziona per le colonne non in associazione. Inoltre, quando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà è `true` , è possibile chiamare questo overload solo per le colonne con binding. Per determinare se una colonna è associata a dati, controllare il <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> valore della proprietà. L'ordinamento delle colonne non vincolate in modalità di associazione non è supportato.  
  
## <a name="custom-sorting"></a>Ordinamento personalizzato  
 È possibile personalizzare <xref:System.Windows.Forms.DataGridView> usando l' `Sort(IComparer)` Overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo o gestendo l' <xref:System.Windows.Forms.DataGridView.SortCompare> evento.  
  
 L' `Sort(IComparer)` Overload del metodo accetta un'istanza di una classe che implementa l' <xref:System.Collections.IComparer> interfaccia come parametro. Questo overload è utile quando si desidera fornire l'ordinamento personalizzato; ad esempio, quando i valori di una colonna non hanno un ordinamento naturale o quando l'ordinamento naturale non è appropriato. In questo caso, non è possibile usare l'ordinamento automatico, ma è comunque possibile che gli utenti vengano ordinati facendo clic sulle intestazioni di colonna. È possibile chiamare questo overload in un gestore per l' <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> evento se non si utilizzano le intestazioni di colonna per la selezione.  
  
> [!NOTE]
> L' `Sort(IComparer)` Overload del metodo funziona solo quando il <xref:System.Windows.Forms.DataGridView> controllo non è associato a un'origine dati esterna e il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> valore della proprietà è `false` . Per personalizzare l'ordinamento delle colonne associato a un'origine dati esterna, è necessario utilizzare le operazioni di ordinamento fornite dall'origine dati. In modalità virtuale è necessario fornire le proprie operazioni di ordinamento per le colonne non in associazione.  
  
 Per usare l' `Sort(IComparer)` Overload del metodo, è necessario creare una classe personalizzata che implementi l' <xref:System.Collections.IComparer> interfaccia. Questa interfaccia richiede che la classe implementi il <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> metodo, al quale <xref:System.Windows.Forms.DataGridView> passa <xref:System.Windows.Forms.DataGridViewRow> gli oggetti come input quando `Sort(IComparer)` viene chiamato l'overload del metodo. In questo modo è possibile calcolare l'ordinamento corretto delle righe in base ai valori di qualsiasi colonna.  
  
 L' `Sort(IComparer)` Overload del metodo non imposta le <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> <xref:System.Windows.Forms.DataGridView.SortOrder%2A> proprietà e, pertanto è sempre necessario impostare la <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> proprietà per visualizzare il glifo di ordinamento.  
  
 In alternativa all'overload del `Sort(IComparer)` metodo, è possibile fornire l'ordinamento personalizzato implementando un gestore per l' <xref:System.Windows.Forms.DataGridView.SortCompare> evento. Questo evento si verifica quando gli utenti fanno clic sulle intestazioni delle colonne configurate per l'ordinamento automatico o quando si chiama l' `Sort(DataGridViewColumn,ListSortDirection)` Overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo. L'evento si verifica per ogni coppia di righe nel controllo, consentendo di calcolare l'ordine corretto.  
  
> [!NOTE]
> L' <xref:System.Windows.Forms.DataGridView.SortCompare> evento non si verifica quando <xref:System.Windows.Forms.DataGridView.DataSource%2A> viene impostata la proprietà o quando il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> valore della proprietà è `true` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Ordinamento dei dati nel controllo DataGridView di Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
