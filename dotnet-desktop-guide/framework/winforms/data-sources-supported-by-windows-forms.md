---
title: Origini dati supportate
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: b4c1c722790688ee638aa4de417664f697df3249
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963520"
---
# <a name="data-sources-supported-by-windows-forms"></a>Origini dati supportate da Windows Form

Tradizionalmente, data binding è stato utilizzato all'interno delle applicazioni per sfruttare i dati archiviati nei database di. Con Windows Forms data binding, è possibile accedere ai dati da database, nonché dati in altre strutture, ad esempio matrici e raccolte, a condizione che siano stati soddisfatti determinati requisiti minimi.  
  
## <a name="structures-to-bind-to"></a>Strutture da associare  

 In Windows Forms, è possibile eseguire l'associazione a un'ampia gamma di strutture, da semplici oggetti (associazione semplice) a elenchi complessi, ad esempio tabelle di dati ADO.NET (Binding complesso). Per l'associazione semplice, Windows Forms supporta l'associazione alle proprietà pubbliche nell'oggetto semplice. Windows Forms associazione basata su elenco richiede in genere che l'oggetto supporti l' <xref:System.Collections.IList> interfaccia o l'interfaccia <xref:System.ComponentModel.IListSource> . Inoltre, se si esegue il binding con tramite un <xref:System.Windows.Forms.BindingSource> componente, è possibile eseguire l'associazione a un oggetto che supporta l' <xref:System.Collections.IEnumerable> interfaccia. Per ulteriori informazioni sulle interfacce correlate ai data binding, vedere [interfacce correlate all'associazione dati](interfaces-related-to-data-binding.md).  
  
 Nell'elenco seguente vengono illustrate le strutture a cui è possibile eseguire il binding in Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Una <xref:System.Windows.Forms.BindingSource> è l'origine dati Windows Forms più comune e funge da proxy tra un'origine dati e controlli di Windows Forms. Il <xref:System.Windows.Forms.BindingSource> modello di utilizzo generale prevede l'associazione dei controlli a <xref:System.Windows.Forms.BindingSource> e l'associazione dell' <xref:System.Windows.Forms.BindingSource> oggetto all'origine dati, ad esempio una tabella di dati ADO.NET o un oggetto business. <xref:System.Windows.Forms.BindingSource>Fornisce servizi che abilitano e migliorano il livello di supporto data binding. Ad esempio, Windows Forms controlli basati su elenco come <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.ComboBox> non supportano direttamente l'associazione alle <xref:System.Collections.IEnumerable> origini dati, tuttavia, è possibile abilitare questo scenario tramite l'associazione tramite un oggetto <xref:System.Windows.Forms.BindingSource> . In questo caso, l'oggetto <xref:System.Windows.Forms.BindingSource> convertirà l'origine dati in un oggetto <xref:System.Collections.IList> .  
  
 Oggetti semplici  
 Windows Forms supporta data binding proprietà del controllo per le proprietà pubbliche nell'istanza di un oggetto usando il <xref:System.Windows.Forms.Binding> tipo. Windows Forms supporta anche l'associazione di controlli basati su elenco, ad esempio un <xref:System.Windows.Forms.ListControl> oggetto a un'istanza di oggetto quando <xref:System.Windows.Forms.BindingSource> si utilizza un.  
  
 matrice o raccolta  
 Per fungere da origine dati, un elenco deve implementare l' <xref:System.Collections.IList> interfaccia. un esempio può essere una matrice che rappresenta un'istanza della <xref:System.Array> classe. Per ulteriori informazioni sulle matrici, vedere [procedura: creare una matrice di oggetti (Visual Basic)](/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 In generale, è consigliabile utilizzare <xref:System.ComponentModel.BindingList%601> quando si creano elenchi di oggetti per data binding. <xref:System.ComponentModel.BindingList%601> è una versione generica dell' <xref:System.ComponentModel.IBindingList> interfaccia. L' <xref:System.ComponentModel.IBindingList> interfaccia estende l' <xref:System.Collections.IList> interfaccia aggiungendo proprietà, metodi ed eventi necessari per la data binding bidirezionale.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms i controlli possono essere associati a origini dati che supportano l' <xref:System.Collections.IEnumerable> interfaccia solo se sono associate tramite un <xref:System.Windows.Forms.BindingSource> componente.  
  
 Oggetti dati ADO.NET  
 ADO.NET fornisce una serie di strutture di dati adatte per l'associazione a. Ognuno di essi varia in base alla complessità e alla complessità.  
  
- <xref:System.Data.DataColumn>. Un <xref:System.Data.DataColumn> è il blocco predefinito essenziale di un oggetto <xref:System.Data.DataTable> , in quanto un numero di colonne comprende una tabella. Ogni oggetto <xref:System.Data.DataColumn> dispone di una <xref:System.Data.DataColumn.DataType%2A> proprietà che determina il tipo di dati contenuti nella colonna (ad esempio, la marca di un'automobile in una tabella che descrive le automobili). È possibile associare in modo semplice un controllo, ad esempio la proprietà di un <xref:System.Windows.Forms.TextBox> controllo, <xref:System.Windows.Forms.Control.Text%2A> a una colonna all'interno di una tabella di dati.  
  
- <xref:System.Data.DataTable>. Un oggetto <xref:System.Data.DataTable> è la rappresentazione di una tabella, con righe e colonne, in ADO.NET. Una tabella di dati contiene due raccolte: <xref:System.Data.DataColumn> , che rappresentano le colonne di dati in una determinata tabella (che in definitiva determinano i tipi di dati che possono essere immessi in tale tabella) e <xref:System.Data.DataRow> , che rappresentano le righe di dati in una tabella specificata. È possibile associare in modo complesso un controllo alle informazioni contenute in una tabella di dati, ad esempio l'associazione del <xref:System.Windows.Forms.DataGridView> controllo a una tabella di dati. Tuttavia, quando si esegue l'associazione a un <xref:System.Data.DataTable> , si è effettivamente associati alla visualizzazione predefinita della tabella.  
  
- <xref:System.Data.DataView>. Un oggetto <xref:System.Data.DataView> è una visualizzazione personalizzata di una singola tabella dati che può essere filtrata o ordinata. Una vista dati è il "snapshot" dei dati usato da controlli con associazione complessa. È possibile eseguire un'associazione semplice o complessa ai dati all'interno di una visualizzazione dati, ma tenere presente che si sta eseguendo il binding a una "immagine" fissa dei dati piuttosto che a un'origine dati pulita e aggiornabile.  
  
- <xref:System.Data.DataSet>. Un oggetto <xref:System.Data.DataSet> è una raccolta di tabelle, relazioni e vincoli dei dati in un database di. È possibile eseguire un'associazione semplice o complessa ai dati all'interno di un set di dati, ma tenere presente che si sta associando a quello predefinito <xref:System.Data.DataViewManager> per <xref:System.Data.DataSet> (vedere il punto di puntamento successivo).  
  
- <xref:System.Data.DataViewManager>. Un oggetto <xref:System.Data.DataViewManager> è una visualizzazione personalizzata dell'intero oggetto <xref:System.Data.DataSet> , analogo a un oggetto <xref:System.Data.DataView> , ma con le relazioni incluse. Con una <xref:System.Data.DataViewManager.DataViewSettings%2A> raccolta è possibile impostare i filtri predefiniti e le opzioni di ordinamento per tutte le visualizzazioni <xref:System.Data.DataViewManager> per una tabella specifica.  
  
## <a name="see-also"></a>Vedere anche

- [Notifica delle modifiche nell'associazione dati dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Associazione dati e Windows Form](data-binding-and-windows-forms.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)
