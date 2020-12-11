---
title: 'Procedura dettagliata: implementare la modalità virtuale nel controllo DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965107"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Forms
Quando si desidera visualizzare quantità molto elevate di dati tabulari in un <xref:System.Windows.Forms.DataGridView> controllo, è possibile impostare la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà su `true` e gestire in modo esplicito l'interazione del controllo con l'archivio dati. In questo modo è possibile ottimizzare le prestazioni del controllo in questa situazione.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce diversi eventi che è possibile gestire per interagire con un archivio dati personalizzato. Questa procedura dettagliata illustra il processo di implementazione di questi gestori di eventi. Nell'esempio di codice in questo argomento viene utilizzata un'origine dati molto semplice a scopo illustrativo. In un'impostazione di produzione, in genere si caricano solo le righe che è necessario visualizzare in una cache e si gestiscono <xref:System.Windows.Forms.DataGridView> gli eventi per interagire con e aggiornare la cache. Per altre informazioni, vedere [implementazione della modalità virtuale con caricamento dati JIT nel controllo Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: implementare la modalità virtuale nel controllo DataGridView Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-implement-virtual-mode"></a>Per implementare la modalità virtuale  
  
1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Il codice seguente contiene alcune inizializzazioni di base. Dichiara alcune variabili che verranno usate nei passaggi successivi, fornisce un `Main` metodo e fornisce un layout di form semplice nel costruttore della classe.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Implementare un gestore per l'evento del form <xref:System.Windows.Forms.Form.Load> che inizializza il <xref:System.Windows.Forms.DataGridView> controllo e popola l'archivio dati con valori di esempio.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento che recupera il valore della cella richiesta dall'archivio dati o l' `Customer` oggetto attualmente in fase di modifica.  
  
     Questo evento si verifica ogni volta che il <xref:System.Windows.Forms.DataGridView> controllo deve disegnare una cella.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.CellValuePushed> evento che archivia un valore di cella modificato nell' `Customer` oggetto che rappresenta la riga modificata. Questo evento si verifica ogni volta che l'utente conferma una modifica del valore di una cella.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.NewRowNeeded> evento che crea un nuovo `Customer` oggetto che rappresenta una riga appena creata.  
  
     Questo evento si verifica ogni volta che l'utente immette la riga per i nuovi record.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.RowValidated> evento che salva le righe nuove o modificate nell'archivio dati.  
  
     Questo evento si verifica ogni volta che l'utente modifica la riga corrente.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento che indica se l' <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento si verificherà quando l'utente segnala la riversione della riga premendo ESC due volte in modalità di modifica o una volta fuori dalla modalità di modifica.  
  
     Per impostazione predefinita, si verifica in seguito alla <xref:System.Windows.Forms.DataGridView.CancelRowEdit> riversione della riga quando le celle della riga corrente sono state modificate a meno che la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> proprietà non sia impostata su `true` nel <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore eventi. Questo evento è utile quando l'ambito del commit viene determinato in fase di esecuzione.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento che ignora i valori dell' `Customer` oggetto che rappresenta la riga corrente.  
  
     Questo evento si verifica quando l'utente segnala la riversione della riga premendo ESC due volte in modalità di modifica o una volta fuori dalla modalità di modifica. Questo evento non si verifica se nessuna cella della riga corrente è stata modificata o se il valore della <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> proprietà è stato impostato su `false` in un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore eventi.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.UserDeletingRow> evento che elimina un `Customer` oggetto esistente dall'archivio dati o rimuove un oggetto non salvato `Customer` che rappresenta una riga appena creata.  
  
     Questo evento si verifica ogni volta che l'utente elimina una riga facendo clic su un'intestazione di riga e premendo il tasto CANC.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementare una `Customers` classe semplice per rappresentare gli elementi dati utilizzati da questo esempio di codice.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Test dell'applicazione  
 È ora possibile testare il form per assicurarsi che si comportano come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il modulo  
  
- Compilare l'applicazione ed eseguirla.  
  
     Viene visualizzato un <xref:System.Windows.Forms.DataGridView> controllo popolato con tre record del cliente. È possibile modificare i valori di più celle in una riga e premere ESC due volte in modalità di modifica e una volta al di fuori della modalità di modifica per ripristinare i valori originali dell'intera riga. Quando si modificano, aggiungono o eliminano righe nel controllo, anche `Customer` gli oggetti nell'archivio dati vengono modificati, aggiunti o eliminati.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione offre una conoscenza di base degli eventi che è necessario gestire per implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo. È possibile migliorare questa applicazione di base in diversi modi:  
  
- Implementare un archivio dati che memorizza nella cache i valori di un database esterno. La cache deve recuperare e scartare i valori in modo da contenere solo gli elementi necessari per la visualizzazione quando si utilizza una piccola quantità di memoria nel computer client.  
  
- Ottimizzare le prestazioni dell'archivio dati in base alle esigenze. È ad esempio possibile che si desideri compensare le connessioni di rete lente anziché le limitazioni della memoria del computer client utilizzando dimensioni della cache maggiori e riducendo al minimo il numero di query di database.  
  
 Per altre informazioni sulla memorizzazione nella cache di valori da un database esterno, vedere [procedura: implementare la modalità virtuale con caricamento dati JIT nel Windows Forms controllo DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Procedura: Implementare la modalità virtuale nel controllo DataGridView di Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
