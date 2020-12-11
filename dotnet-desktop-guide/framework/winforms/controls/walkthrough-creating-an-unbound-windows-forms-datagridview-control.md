---
title: Creazione di un controllo DataGridView non associato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967000"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Procedura dettagliata: Creazione di un controllo DataGridView di Windows Forms non associato
È possibile che si desideri visualizzare spesso dati tabulari che non provengono da un database di. È ad esempio possibile che si desideri visualizzare il contenuto di una matrice bidimensionale di stringhe. La <xref:System.Windows.Forms.DataGridView> classe fornisce un modo semplice e altamente personalizzabile per visualizzare i dati senza binding a un'origine dati. In questa procedura dettagliata viene illustrato come popolare un <xref:System.Windows.Forms.DataGridView> controllo e come gestire l'aggiunta e l'eliminazione di righe in modalità "non associata". Per impostazione predefinita, l'utente può aggiungere nuove righe. Per evitare l'aggiunta di righe, impostare la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà su `false` .  
  
 Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un controllo DataGridView Windows Forms non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Per usare un controllo DataGridView non associato  
  
1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene le dichiarazioni di variabile e il `Main` metodo seguenti.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Implementare un `SetupLayout` metodo nella definizione di classe del form per impostare il layout del modulo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Creare un `SetupDataGridView` metodo per impostare le <xref:System.Windows.Forms.DataGridView> colonne e le proprietà.  
  
     Questo metodo aggiunge prima di tutto il <xref:System.Windows.Forms.DataGridView> controllo alla raccolta del form <xref:System.Windows.Forms.Control.Controls%2A> . Il numero di colonne da visualizzare viene quindi impostato utilizzando la <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> Proprietà. Lo stile predefinito per le intestazioni di colonna viene impostato impostando <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> le <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> proprietà, e <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> dell'oggetto <xref:System.Windows.Forms.DataGridViewCellStyle> restituito dalla <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> Proprietà.  
  
     Vengono impostate le proprietà layout e aspetto, quindi vengono assegnati i nomi delle colonne. Quando questo metodo viene chiuso, il <xref:System.Windows.Forms.DataGridView> controllo è pronto per essere popolato.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Creare un `PopulateDataGridView` metodo per aggiungere righe al <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Ogni riga rappresenta un brano e le relative informazioni associate.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. Con i metodi di utilità disponibili, è possibile associare i gestori eventi.  
  
     Si gestiranno gli eventi dei pulsanti **Aggiungi** ed **Elimina** <xref:System.Windows.Forms.Control.Click> , l'evento del form <xref:System.Windows.Forms.Form.Load> e l' <xref:System.Windows.Forms.DataGridView> evento del controllo <xref:System.Windows.Forms.DataGridView.CellFormatting> .  
  
     Quando viene generato l'evento del pulsante **Aggiungi** <xref:System.Windows.Forms.Control.Click> , viene aggiunta una nuova riga vuota a <xref:System.Windows.Forms.DataGridView> .  
  
     Quando viene generato l'evento del pulsante **Elimina** , <xref:System.Windows.Forms.Control.Click> la riga selezionata viene eliminata, a meno che non si tratti della riga per i nuovi record, che consente all'utente di aggiungere nuove righe. Questa riga è sempre l'ultima riga nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Quando <xref:System.Windows.Forms.Form.Load> viene generato l'evento del modulo, `SetupLayout` `SetupDataGridView` `PopulateDataGridView` vengono chiamati i metodi di utilità, e.  
  
     Quando <xref:System.Windows.Forms.DataGridView.CellFormatting> viene generato l'evento, ogni cella della `Date` colonna viene formattata come data estesa, a meno che non sia possibile analizzare il valore della cella.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Test dell'applicazione  
 È ora possibile testare il form per assicurarsi che si comportano come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il modulo  
  
- Premere F5 per eseguire l'applicazione.  
  
     Verrà <xref:System.Windows.Forms.DataGridView> visualizzato un controllo che Visualizza i brani elencati in `PopulateDataGridView` . È possibile aggiungere nuove righe con il pulsante **Aggiungi riga** ed è possibile eliminare le righe selezionate con il pulsante **Elimina riga** . Il controllo non associato <xref:System.Windows.Forms.DataGridView> è l'archivio dati e i relativi dati sono indipendenti da qualsiasi origine esterna, ad esempio un oggetto <xref:System.Data.DataSet> o una matrice.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione offre una conoscenza di base delle <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: creare colonne Read-Only nel controllo Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Controllare l'input dell'utente per gli errori correlati al database. Per ulteriori informazioni, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Visualizzazione di dati nel controllo DataGridView Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un controllo DataGridView di Windows Forms non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
