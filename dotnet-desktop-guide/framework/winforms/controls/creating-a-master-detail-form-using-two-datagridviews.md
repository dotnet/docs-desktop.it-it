---
title: 'Procedura dettagliata: creare un form Master-Details con due controlli DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: d6057eb16e8fc32c269d3013ee99cc1f276ecab6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951147"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Procedura dettagliata: Creazione di un modulo Master-Details usando due controlli DataGridView di Windows Forms

Uno degli scenari più comuni per l'utilizzo del <xref:System.Windows.Forms.DataGridView> controllo è costituito dal formato *Master/Details* , in cui viene visualizzata una relazione padre/figlio tra due tabelle di database. La selezione di righe nella tabella master comporta l'aggiornamento della tabella dei dettagli con i dati figlio corrispondenti.

L'implementazione di un form Master-Details semplifica l'utilizzo dell'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e il <xref:System.Windows.Forms.BindingSource> componente. In questa procedura dettagliata verrà compilato il form utilizzando due <xref:System.Windows.Forms.DataGridView> controlli e due <xref:System.Windows.Forms.BindingSource> componenti. Nel modulo vengono visualizzate due tabelle correlate nel database di esempio Northwind SQL Server: `Customers` e `Orders` . Al termine, sarà presente un modulo che Mostra tutti i clienti del database nel database master <xref:System.Windows.Forms.DataGridView> e tutti gli ordini per il cliente selezionato nei dettagli <xref:System.Windows.Forms.DataGridView> .

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un form Master-Details con due Windows Forms controlli DataGridView](create-a-master-detail-form-using-two-datagridviews.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questo scenario, saranno necessari gli elementi seguenti:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del modulo

#### <a name="to-create-a-masterdetail-form"></a>Per creare un form Master-Details

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene due <xref:System.Windows.Forms.DataGridView> controlli e due <xref:System.Windows.Forms.BindingSource> componenti. Il codice seguente fornisce l'inizializzazione dei form di base e include un `Main` metodo. Se si usa la finestra di progettazione di Visual Studio per creare il form, è possibile usare il codice generato dalla finestra di progettazione anziché questo codice, ma assicurarsi di usare i nomi visualizzati nelle dichiarazioni di variabile qui.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database. In questo esempio viene utilizzato un `GetData` metodo che popola un <xref:System.Data.DataSet> oggetto, aggiunge un <xref:System.Data.DataRelation> oggetto al set di dati e associa i <xref:System.Windows.Forms.BindingSource> componenti. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Implementare un gestore per l'evento del form <xref:System.Windows.Forms.Form.Load> che associa i <xref:System.Windows.Forms.DataGridView> controlli ai <xref:System.Windows.Forms.BindingSource> componenti e chiama il `GetData` metodo. Nell'esempio seguente viene incluso il codice che ridimensiona <xref:System.Windows.Forms.DataGridView> le colonne per adattarle ai dati visualizzati.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Test dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Compilare l'applicazione ed eseguirla.

  Vengono visualizzati due <xref:System.Windows.Forms.DataGridView> controlli, uno sopra l'altro. I clienti della tabella Northwind sono in primo piano `Customers` e sono nella parte inferiore `Orders` corrispondente al cliente selezionato. Quando si selezionano righe diverse nella parte superiore <xref:System.Windows.Forms.DataGridView> , il contenuto della modifica inferiore di <xref:System.Windows.Forms.DataGridView> conseguenza.

## <a name="next-steps"></a>Passaggi successivi

Questa applicazione offre una conoscenza di base delle <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:

- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: creare colonne Read-Only nel controllo Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [procedura dettagliata: convalida dei dati nel controllo DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).

- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzazione di dati nel controllo DataGridView Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un modulo Master-Details usando due controlli DataGridView di Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information)
