---
title: "Procedura dettagliata: Esecuzione di un'operazione in background"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: ad0955937965c89b52648e37cd151e0cd266e527
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964690"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Procedura dettagliata: Esecuzione di un'operazione in background

Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.

Per un elenco completo del codice usato in questo esempio, vedere [procedura: eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).

## <a name="run-an-operation-in-the-background"></a>Eseguire un'operazione in background

1. Con il modulo attivo nel Progettazione Windows Form in Visual Studio, trascinare due <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form, quindi impostare le `Name` <xref:System.Windows.Forms.Control.Text%2A> proprietà e dei pulsanti in base alla tabella seguente.

    |Pulsante|Name|Testo|
    |------------|----------|----------|
    |`button1`|`startBtn`|**Inizia**|
    |`button2`|`cancelBtn`|**Annulla**|

2. Aprire la **casella degli strumenti**, fare clic sulla scheda **componenti** , quindi trascinare il <xref:System.ComponentModel.BackgroundWorker> componente nel form.

     Il `backgroundWorker1` componente verrà visualizzato nella **barra dei componenti**.

3. Nella finestra **Proprietà** impostare la proprietà <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> su `true`.

4. Nella finestra **Proprietà** fare clic sul pulsante **eventi** , quindi fare doppio clic sugli <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventi e per creare i gestori eventi.

5. Inserire il codice che richiede molto tempo nel <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi.

6. Estrarre tutti i parametri richiesti dall'operazione dalla <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs> parametro.

7. Assegnare il risultato del calcolo alla <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> proprietà di <xref:System.ComponentModel.DoWorkEventArgs> .

     Questa operazione sarà disponibile per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. Inserire il codice per recuperare il risultato dell'operazione nel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. Implementare il metodo `TimeConsumingOperation`.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. Nella Progettazione Windows Form fare doppio clic `startButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore eventi.

11. Chiamare il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento per `startButton` .

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. Nella Progettazione Windows Form fare doppio clic `cancelButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore eventi.

13. Chiamare il <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodo nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento per `cancelButton` .

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. All'inizio del file importare gli spazi dei nomi System. ComponentModel e System. Threading.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. Premere **F6** per compilare la soluzione, quindi premere **CTRL** + **F5** per eseguire l'applicazione all'esterno del debugger.

    > [!NOTE]
    > Se si preme **F5** per eseguire l'applicazione nel debugger, l'eccezione generata nel `TimeConsumingOperation` metodo viene rilevata e visualizzata dal debugger. Quando si esegue l'applicazione all'esterno del debugger, <xref:System.ComponentModel.BackgroundWorker> gestisce l'eccezione e la memorizza nella cache nella <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> proprietà di <xref:System.ComponentModel.RunWorkerCompletedEventArgs> .

16. Fare clic sul pulsante **Start** per eseguire un'operazione asincrona, quindi fare clic sul pulsante **Annulla** per arrestare un'operazione asincrona in esecuzione.

     Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.

## <a name="next-steps"></a>Passaggi successivi

- Implementare un modulo che segnala lo stato di avanzamento di un'operazione asincrona. Per altre informazioni, vedere [procedura: implementare un form che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md).

- Implementare una classe che supporta il modello asincrono per i componenti. Per altre informazioni, vedere [implementazione del modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern).

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)
- [Componente BackgroundWorker](backgroundworker-component.md)
