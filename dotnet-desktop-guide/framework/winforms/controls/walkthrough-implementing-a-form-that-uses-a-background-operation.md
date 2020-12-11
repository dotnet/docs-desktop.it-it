---
title: "Procedura dettagliata: Implementazione di un modulo che usa un'operazione in background"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: bdd82b0f32f93fbcdd5713bfb9ba9081f653298b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964711"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a>Procedura dettagliata: Implementazione di un modulo che usa un'operazione in background

Se il completamento di un'operazione richiede molto tempo e non si vuole che l'interfaccia utente (UI) interrompa la risposta o il blocco, è possibile usare la <xref:System.ComponentModel.BackgroundWorker> classe per eseguire l'operazione su un altro thread.

In questa procedura dettagliata viene illustrato come utilizzare la <xref:System.ComponentModel.BackgroundWorker> classe per eseguire calcoli dispendiosi in termini di tempo in background, mentre l'interfaccia utente rimane attiva.  Nel corso della procedura, un'applicazione calcola i numeri Fibonacci in modo asincrono. Sebbene il calcolo di un numero Fibonacci a molte cifre possa impiegare una notevole quantità di tempo, il thread principale dell'interfaccia utente non verrà interrotto da questa operazione e la capacità di risposta del modulo resterà inalterata durante il calcolo.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione di un'applicazione basata su Windows

- Creazione di un oggetto <xref:System.ComponentModel.BackgroundWorker> nel form

- Aggiunta dei gestori eventi asincroni

- Aggiunta dei report sullo stato di avanzamento e supporto per l'annullamento

Per il listato completo del codice utilizzato in questo esempio, vedere [Procedura: Implementare un modulo che utilizza un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md).

## <a name="create-a-form-that-uses-a-background-operation"></a>Creazione di un modulo che utilizza un'operazione in background

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato `BackgroundWorkerExample` (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).

2. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Form1** e scegliere **Rinomina** dal menu di scelta rapida. Modificare il nome file in `FibonacciCalculator`. Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice '`Form1`'.

3. Trascinare un <xref:System.Windows.Forms.NumericUpDown> controllo dalla **casella degli strumenti** nel form. Impostare la <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> proprietà su `1` e la <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> proprietà su `91` .

4. Aggiungere due <xref:System.Windows.Forms.Button> controlli al form.

5. Rinominare il primo <xref:System.Windows.Forms.Button> controllo `startAsyncButton` e impostare la <xref:System.Windows.Forms.Control.Text%2A> proprietà su `Start Async` . Rinominare il secondo <xref:System.Windows.Forms.Button> controllo `cancelAsyncButton` e impostare la <xref:System.Windows.Forms.Control.Text%2A> proprietà su `Cancel Async` . Impostare la relativa <xref:System.Windows.Forms.Control.Enabled%2A> proprietà su `false` .

6. Creare un gestore eventi per entrambi gli <xref:System.Windows.Forms.Button> eventi dei controlli <xref:System.Windows.Forms.Control.Click> . Per informazioni dettagliate, vedere [Procedura: Creare le impostazioni delle applicazioni usando la finestra di progettazione](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

7. Trascinare un <xref:System.Windows.Forms.Label> controllo dalla **casella degli strumenti** nel form e rinominarlo `resultLabel` .

8. Trascinare un <xref:System.Windows.Forms.ProgressBar> controllo dalla **casella degli strumenti** nel form.

## <a name="create-a-backgroundworker-with-the-designer"></a>Creare un BackgroundWorker con la finestra di progettazione

È possibile creare <xref:System.ComponentModel.BackgroundWorker> per l'operazione asincrona utilizzando Progettazione **Windows** **form**.

Dalla scheda **componenti** della **casella degli strumenti** trascinare un oggetto nel <xref:System.ComponentModel.BackgroundWorker> form.

## <a name="add-asynchronous-event-handlers"></a>Aggiungere gestori eventi asincroni

A questo punto è possibile aggiungere i gestori eventi per gli <xref:System.ComponentModel.BackgroundWorker> eventi asincroni del componente. L'operazione dispendiosa in termini di tempo che verrà eseguita in background, ossia quella che calcola i numeri Fibonacci, viene chiamata da uno di questi gestori eventi.

1. Nella finestra **Proprietà** , con il <xref:System.ComponentModel.BackgroundWorker> componente ancora selezionato, fare clic sul pulsante **eventi** . Fare doppio clic <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> sugli eventi e per creare i gestori eventi. Per altre informazioni sulle modalità di utilizzo dei gestori eventi, vedere [Procedura: creare le impostazioni delle applicazioni usando la finestra di progettazione](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

2. Creare nel form un nuovo metodo denominato `ComputeFibonacci`. L'operazione verrà effettivamente svolta da questo metodo che verrà eseguito in background. Il codice dimostra l'implementazione ricorsiva dell'algoritmo Fibonacci che è decisamente inefficiente e esponenzialmente impiega più tempo per completare i numeri a molte cifre. Viene impiegato per dimostrare come un'operazione possa provocare lunghi ritardi nell'applicazione.

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. Nel <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi aggiungere una chiamata al `ComputeFibonacci` metodo. Prendere il primo parametro per `ComputeFibonacci` dalla <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> proprietà dell'oggetto <xref:System.ComponentModel.DoWorkEventArgs> . I <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.DoWorkEventArgs> parametri e verranno usati in seguito per la creazione di report sullo stato di avanzamento e il supporto dell'annullamento. Assegnare il valore restituito da `ComputeFibonacci` alla <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> proprietà di <xref:System.ComponentModel.DoWorkEventArgs> . Questo risultato sarà disponibile per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi.

    > [!NOTE]
    > Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi non fa riferimento `backgroundWorker1` direttamente alla variabile di istanza, in quanto questo associa questo gestore eventi a un'istanza specifica di <xref:System.ComponentModel.BackgroundWorker> . Al contrario, un riferimento all'oggetto <xref:System.ComponentModel.BackgroundWorker> che ha generato l'evento viene recuperato dal `sender` parametro. Questo è importante quando il modulo ospita più di uno <xref:System.ComponentModel.BackgroundWorker> . È anche importante non modificare gli oggetti dell'interfaccia utente nel <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi. Comunicare invece con l'interfaccia utente tramite gli <xref:System.ComponentModel.BackgroundWorker> eventi.

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. Nel `startAsyncButton` <xref:System.Windows.Forms.Control.Click> gestore eventi del controllo aggiungere il codice che avvia l'operazione asincrona.

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. Nel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento assegnare il risultato del calcolo al `resultLabel` controllo.

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a>Aggiunta dei report sullo stato di avanzamento e supporto per l'annullamento

Per le operazioni asincrone che impiegano molto tempo è spesso opportuno notificare all'utente lo stato di avanzamento e permettergli di annullare eventualmente l'operazione. La <xref:System.ComponentModel.BackgroundWorker> classe fornisce un evento che consente di pubblicare lo stato di avanzamento dell'operazione in background. Fornisce inoltre un flag che consente al codice del ruolo di lavoro di rilevare una chiamata a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> e interrompersi.

### <a name="implement-progress-reporting"></a>Implementare i report di stato

1. Nella finestra **Proprietà** selezionare `backgroundWorker1`. Impostare le <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> proprietà e su `true` .

2. Nel modulo `FibonacciCalculator` dichiarare due variabili che verranno utilizzate per tenere traccia dello stato di avanzamento.

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. Aggiunge un gestore eventi per l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>. Nel <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore dell'evento aggiornare <xref:System.Windows.Forms.ProgressBar> con la <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> proprietà del <xref:System.ComponentModel.ProgressChangedEventArgs> parametro.

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a>Implementare il supporto per l'annullamento

1. Nel `cancelAsyncButton` <xref:System.Windows.Forms.Control.Click> gestore eventi del controllo aggiungere il codice che annulla l'operazione asincrona.

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. I seguenti frammenti di codice nel metodo `ComputeFibonacci` restituiscono lo stato di avanzamento e supportano l'annullamento.

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a>Checkpoint

A questo punto è possibile compilare ed eseguire l'applicazione Fibonacci Calculator.

Premere **F5** per compilare ed eseguire l'applicazione.

Mentre il calcolo è in esecuzione in background, verrà visualizzato lo <xref:System.Windows.Forms.ProgressBar> stato di avanzamento del calcolo verso il completamento. È anche possibile annullare l'operazione in sospeso.

Per i numeri con poche cifre, il calcolo dovrebbe essere molto rapido, ma per i numeri con tante cifre, si potrebbe notare un considerevole ritardo. Se si immette il valore 30 o superiore, il ritardo sarà di diversi secondi, a seconda della velocità del computer. Per i valori maggiori di 40, potrebbero essere necessari diversi minuti o ore per completare il calcolo. Mentre il calcolatore è impegnato a calcolare un numero Fibonacci con tante cifre, il modulo può essere spostato liberamente, ridotto a icona, ingrandito e persino chiuso in quanto il thread principale dell'interfaccia utente non è in attesa della fine del calcolo.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato implementato un modulo che usa un <xref:System.ComponentModel.BackgroundWorker> componente per eseguire un calcolo in background, è possibile esplorare altre possibilità per le operazioni asincrone:

- Usare più <xref:System.ComponentModel.BackgroundWorker> oggetti per diverse operazioni simultanee.

- Per eseguire il debug dell'applicazione con multithreading, vedere [Procedura: utilizzare la finestra Thread](/visualstudio/debugger/how-to-use-the-threads-window).

- Implementare il componente che supporta il modello di programmazione asincrona. Per ulteriori informazioni, vedere [Cenni preliminari sul modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview).

    > [!CAUTION]
    > L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi. Vedere [Procedure consigliate per l'uso del threading gestito](/dotnet/standard/threading/managed-threading-best-practices) prima di implementare soluzioni che usano il multithreading.

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [Threading gestito](/dotnet/standard/threading/index)
- [Suggerimenti per l'utilizzo del threading gestito](/dotnet/standard/threading/managed-threading-best-practices)
- [Cenni preliminari sul modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Procedura dettagliata: Esecuzione di un'operazione in background](walkthrough-running-an-operation-in-the-background.md)
- [Componente BackgroundWorker](backgroundworker-component.md)
