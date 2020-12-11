---
title: Panoramica del controllo ComboBox
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951215"
---
# <a name="combobox-control-overview-windows-forms"></a>Cenni preliminari sul controllo ComboBox (Windows Form)
Il <xref:System.Windows.Forms.ComboBox> controllo Windows Forms viene usato per visualizzare i dati in una casella combinata a discesa. Per impostazione predefinita, il <xref:System.Windows.Forms.ComboBox> controllo viene visualizzato in due parti: la parte superiore è una casella di testo che consente all'utente di digitare un elemento elenco. La seconda parte è una casella di riepilogo in cui viene visualizzato un elenco di elementi da cui l'utente può selezionarne uno. Per ulteriori informazioni sugli altri stili della casella combinata, vedere [quando utilizzare un Windows Forms ComboBox anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 La <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> proprietà restituisce un valore integer che corrisponde all'elemento di elenco selezionato. È possibile modificare a livello di codice l'elemento selezionato modificando il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore nel codice. l'elemento corrispondente nell'elenco verrà visualizzato nella casella di testo della casella combinata. Se non è selezionato alcun elemento, il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è-1. Se il primo elemento dell'elenco è selezionato, il <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valore è 0. La <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> proprietà è simile a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , ma restituisce l'elemento stesso, in genere un valore stringa. La <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà riflette il numero di elementi nell'elenco e il valore della <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> proprietà è sempre un valore maggiore del valore massimo possibile <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> perché <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> è in base zero.  
  
 Per aggiungere o eliminare elementi in un <xref:System.Windows.Forms.ComboBox> controllo, usare il <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A> metodo, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> . In alternativa, è possibile aggiungere elementi all'elenco utilizzando la <xref:System.Windows.Forms.ComboBox.Items%2A> proprietà nella finestra di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- [Panoramica del controllo ListBox](listbox-control-overview-windows-forms.md)
- [Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Procedura: Accedere a elementi specifici in un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Procedura: Associare un controllo ComboBox o ListBox di Windows Forms ai dati](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
- [Procedura: Creare una tabella di ricerca per un controllo ComboBox, ListBox o CheckedListBox di Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
