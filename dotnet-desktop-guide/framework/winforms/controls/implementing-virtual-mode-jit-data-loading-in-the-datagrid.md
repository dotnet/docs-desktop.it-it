---
title: Implementazione della modalità virtuale con caricamento dati JIT nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
ms.openlocfilehash: 5f1d3faad0bb05305086bc46076137f5b1202cb6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961588"
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form

Un motivo per implementare la modalità virtuale nel <xref:System.Windows.Forms.DataGridView> controllo consiste nel recuperare i dati solo quando è necessario. Questa operazione viene chiamata *caricamento dati JIT*.  
  
 Se si utilizza una tabella di grandi dimensioni in un database remoto, ad esempio, è possibile evitare ritardi di avvio recuperando solo i dati necessari per la visualizzazione e il recupero di dati aggiuntivi solo quando l'utente scorre le nuove righe nella visualizzazione. Se nei computer client in cui è in esecuzione l'applicazione è disponibile una quantità limitata di memoria per l'archiviazione dei dati, potrebbe essere necessario rimuovere i dati non utilizzati durante il recupero di nuovi valori dal database.  
  
 Le sezioni seguenti descrivono come usare un <xref:System.Windows.Forms.DataGridView> controllo con una cache just-in-time.  
  
 Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: implementare la modalità virtuale con caricamento dati JIT nel controllo Windows Forms DataGridView](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="the-form"></a>Il modulo  

 Nell'esempio di codice seguente viene definito un form contenente un controllo di sola lettura <xref:System.Windows.Forms.DataGridView> che interagisce con un `Cache` oggetto tramite un <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore eventi. L' `Cache` oggetto gestisce i valori archiviati localmente e utilizza un `DataRetriever` oggetto per recuperare i valori dalla tabella Orders del database Northwind di esempio. L' `DataRetriever` oggetto, che implementa l' `IDataPageRetriever` interfaccia richiesta dalla `Cache` classe, viene utilizzato anche per inizializzare le <xref:System.Windows.Forms.DataGridView> righe e le colonne del controllo.  
  
 I `IDataPageRetriever` `DataRetriever` tipi, e `Cache` sono descritti più avanti in questo argomento.  
  
> [!NOTE]
> L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>Interfaccia IDataPageRetriever  

 Nell'esempio di codice seguente viene definita l' `IDataPageRetriever` interfaccia implementata dalla `DataRetriever` classe. L'unico metodo dichiarato in questa interfaccia è il `SupplyPageOfData` metodo, che richiede un indice di riga iniziale e un conteggio del numero di righe in una singola pagina di dati. Questi valori vengono utilizzati dall'implementatore per recuperare un subset di dati da un'origine dati.  
  
 Un `Cache` oggetto usa un'implementazione di questa interfaccia durante la costruzione per caricare due pagine iniziali di dati. Ogni volta che è necessario un valore non memorizzato nella cache, nella cache viene eliminata una di queste pagine e viene richiesta una nuova pagina che contiene il valore da `IDataPageRetriever` .  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>Classe DataRetriever  

 Nell'esempio di codice seguente viene definita la `DataRetriever` classe, che implementa l' `IDataPageRetriever` interfaccia per recuperare le pagine di dati da un server. La `DataRetriever` classe fornisce inoltre `Columns` le `RowCount` proprietà e, <xref:System.Windows.Forms.DataGridView> utilizzate dal controllo per creare le colonne necessarie e aggiungere il numero appropriato di righe vuote alla <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta. L'aggiunta delle righe vuote è necessaria in modo che il controllo si comporti come se contiene tutti i dati nella tabella. Ciò significa che la casella di scorrimento della barra di scorrimento avrà le dimensioni appropriate e l'utente sarà in grado di accedere a qualsiasi riga della tabella. Le righe vengono riempite dal <xref:System.Windows.Forms.DataGridView.CellValueNeeded> gestore eventi solo quando vengono visualizzate.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>Classe cache  

 Nell'esempio di codice seguente viene definita la `Cache` classe, che gestisce due pagine di dati popolate tramite un' `IDataPageRetriever` implementazione. La `Cache` classe definisce una `DataPage` struttura interna, che contiene un oggetto <xref:System.Data.DataTable> per archiviare i valori in una singola pagina della cache e che calcola gli indici di riga che rappresentano i limiti superiore e inferiore della pagina.  
  
 La `Cache` classe carica due pagine di dati in fase di costruzione. Ogni volta che l' <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento richiede un valore, l' `Cache` oggetto determina se il valore è disponibile in una delle due pagine e, in caso affermativo, lo restituisce. Se il valore non è disponibile localmente, l' `Cache` oggetto determina quale delle due pagine è più lontana dalle righe attualmente visualizzate e sostituisce la pagina con una nuova che contiene il valore richiesto, che viene quindi restituito.  
  
 Supponendo che il numero di righe in una pagina di dati corrisponda al numero di righe che possono essere visualizzate contemporaneamente sullo schermo, questo modello consente agli utenti di eseguire il paging della tabella per tornare in modo efficiente alla pagina visualizzata più di recente.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>Ulteriori considerazioni  

 Gli esempi di codice precedenti vengono forniti come dimostrazione del caricamento di dati JIT. Sarà necessario modificare il codice in base alle proprie esigenze per ottenere la massima efficienza. Come minimo, sarà necessario scegliere un valore appropriato per il numero di righe per pagina di dati nella cache. Questo valore viene passato al `Cache` costruttore. Il numero di righe per pagina deve essere inferiore al numero di righe che possono essere visualizzate contemporaneamente nel <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Per ottenere risultati ottimali, sarà necessario eseguire test delle prestazioni e test di usabilità per determinare i requisiti del sistema e degli utenti. Alcuni fattori che è necessario considerare includono la quantità di memoria nei computer client che eseguono l'applicazione, la larghezza di banda disponibile della connessione di rete utilizzata e la latenza del server utilizzata. La larghezza di banda e la latenza devono essere determinate in momenti di picco sull'utilizzo.  
  
 Per migliorare le prestazioni di scorrimento dell'applicazione, è possibile aumentare la quantità di dati archiviati localmente. Per migliorare il tempo di avvio, tuttavia, è necessario evitare il caricamento iniziale di troppi dati. Potrebbe essere necessario modificare la `Cache` classe per aumentare il numero di pagine di dati che è in grado di archiviare. L'utilizzo di più pagine di dati può migliorare l'efficienza dello scorrimento, ma sarà necessario determinare il numero ideale di righe in una pagina di dati, a seconda della larghezza di banda disponibile e della latenza del server. Con le pagine più piccole, l'accesso al server sarà più frequente, ma il tempo necessario per restituire i dati richiesti sarà inferiore. Se la latenza è maggiore di un problema rispetto alla larghezza di banda, è consigliabile utilizzare pagine di dati di dimensioni maggiori.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Procedura: Implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView di Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
