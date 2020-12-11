---
title: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 57dc95fc16d77ee1492f53bf57eac001a343ca8f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951166"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Procedura: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox di Windows Forms

Può risultare utile visualizzare i dati all'interno di un Windows Form in un formato facilmente riconoscibile dall'utente, ma memorizzare gli stessi dati in un formato che consenta una migliore gestione da parte del programma. Ad esempio un form di ordinazione per generi alimentari può visualizzare le voci di menu ordinate in base al nome in una casella di riepilogo, mentre la tabella dati per la registrazione dell'ordine può contenere i numeri univoci di identificazione corrispondenti a ogni piatto. Nelle tabelle seguenti viene mostrato un esempio di memorizzazione e visualizzazione dei dati contenuti in un form di ordinazione per generi alimentari.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantità|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|Nome|  
|--------|----------|  
|12|Patate|  
|13|Pollo|  
  
 In questo scenario, in una tabella, **tabella OrderDetailsTable**, sono archiviate le informazioni effettive di cui si è interessati per la visualizzazione e il salvataggio. Per risparmiare spazio, però, la memorizzazione avviene in modo piuttosto criptico. L'altra tabella, **ItemTable**, contiene solo informazioni correlate all'aspetto per cui il numero di ID è equivalente al nome del cibo e niente sugli ordini di cibo effettivi.  
  
 **ItemTable** è connesso al <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> controllo, o <xref:System.Windows.Forms.CheckedListBox> tramite tre proprietà. La `DataSource` proprietà contiene il nome della tabella. La `DisplayMember` proprietà contiene la colonna di dati della tabella che si desidera visualizzare nel controllo (il nome del cibo). La `ValueMember` proprietà contiene la colonna di dati della tabella con le informazioni archiviate (il numero di ID).  
  
 **Tabella OrderDetailsTable** è connesso al controllo mediante la relativa raccolta Bindings, a cui si accede tramite la <xref:System.Windows.Forms.Control.DataBindings%2A> Proprietà. Quando si aggiunge un oggetto di associazione alla raccolta, si connette una proprietà del controllo a un membro dati specifico (la colonna di numeri ID) in un'origine dati ( **tabella OrderDetailsTable**). Quando nel controllo viene effettuata una selezione, l'input del form viene salvato in questa tabella.  
  
### <a name="to-create-a-lookup-table"></a>Per creare una tabella di ricerca  
  
1. Aggiungere un controllo <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al form.  
  
2. Effettuare la connessione all'origine dati.  
  
3. Stabilire una relazione dati tra le due tabelle. Vedere [Introduzione agli oggetti DataRelation](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).  
  
4. Impostare le proprietà seguenti, nel codice o nella finestra di progettazione.  
  
    |Proprietà|Impostazione|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Nella tabella sono contenute le informazioni relative ai numeri ID equivalenti alle diverse voci. Nello scenario precedente, si tratta di `ItemTable` .|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|La colonna della tabella dell'origine dati che si vuole visualizzare nel controllo. Nello scenario precedente, questo è `"Name"` (per impostare nel codice, usare le virgolette).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|La colonna della tabella di origine dati che contiene le informazioni memorizzate. Nello scenario precedente, questo è `"ID"` (per impostare nel codice, usare le virgolette).|  
  
5. In una routine, chiamare il metodo <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> della classe <xref:System.Windows.Forms.ControlBindingsCollection> per associare la proprietà <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del controllo alla tabella che registra l'input del form. È anche possibile eseguire questa operazione nella finestra di progettazione anziché nel codice, accedendo alla proprietà del controllo <xref:System.Windows.Forms.Control.DataBindings%2A> nella finestra **Proprietà** . Nello scenario precedente, si tratta di `OrderDetailsTable` e la colonna è `"ItemID"` .  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Associazione dati e Windows Form](../data-binding-and-windows-forms.md)
- [Panoramica del controllo ListBox](listbox-control-overview-windows-forms.md)
- [Panoramica del controllo ComboBox](combobox-control-overview-windows-forms.md)
- [Panoramica del controllo CheckedListBox](checkedlistbox-control-overview-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
