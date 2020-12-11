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
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="45a7b-102">Procedura dettagliata: Esecuzione di un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="45a7b-102">Walkthrough: Running an Operation in the Background</span></span>

<span data-ttu-id="45a7b-103">Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="45a7b-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>

<span data-ttu-id="45a7b-104">Per un elenco completo del codice usato in questo esempio, vedere [procedura: eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="45a7b-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>

## <a name="run-an-operation-in-the-background"></a><span data-ttu-id="45a7b-105">Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="45a7b-105">Run an operation in the background</span></span>

1. <span data-ttu-id="45a7b-106">Con il modulo attivo nel Progettazione Windows Form in Visual Studio, trascinare due <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form, quindi impostare le `Name` <xref:System.Windows.Forms.Control.Text%2A> proprietà e dei pulsanti in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="45a7b-106">With your form active in the Windows Forms Designer in Visual Studio, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>

    |<span data-ttu-id="45a7b-107">Pulsante</span><span class="sxs-lookup"><span data-stu-id="45a7b-107">Button</span></span>|<span data-ttu-id="45a7b-108">Name</span><span class="sxs-lookup"><span data-stu-id="45a7b-108">Name</span></span>|<span data-ttu-id="45a7b-109">Testo</span><span class="sxs-lookup"><span data-stu-id="45a7b-109">Text</span></span>|
    |------------|----------|----------|
    |`button1`|`startBtn`|<span data-ttu-id="45a7b-110">**Inizia**</span><span class="sxs-lookup"><span data-stu-id="45a7b-110">**Start**</span></span>|
    |`button2`|`cancelBtn`|<span data-ttu-id="45a7b-111">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="45a7b-111">**Cancel**</span></span>|

2. <span data-ttu-id="45a7b-112">Aprire la **casella degli strumenti**, fare clic sulla scheda **componenti** , quindi trascinare il <xref:System.ComponentModel.BackgroundWorker> componente nel form.</span><span class="sxs-lookup"><span data-stu-id="45a7b-112">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>

     <span data-ttu-id="45a7b-113">Il `backgroundWorker1` componente verrà visualizzato nella **barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="45a7b-113">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>

3. <span data-ttu-id="45a7b-114">Nella finestra **Proprietà** impostare la proprietà <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="45a7b-114">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>

4. <span data-ttu-id="45a7b-115">Nella finestra **Proprietà** fare clic sul pulsante **eventi** , quindi fare doppio clic sugli <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventi e per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-115">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>

5. <span data-ttu-id="45a7b-116">Inserire il codice che richiede molto tempo nel <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-116">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>

6. <span data-ttu-id="45a7b-117">Estrarre tutti i parametri richiesti dall'operazione dalla <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs> parametro.</span><span class="sxs-lookup"><span data-stu-id="45a7b-117">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>

7. <span data-ttu-id="45a7b-118">Assegnare il risultato del calcolo alla <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> proprietà di <xref:System.ComponentModel.DoWorkEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="45a7b-118">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>

     <span data-ttu-id="45a7b-119">Questa operazione sarà disponibile per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-119">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. <span data-ttu-id="45a7b-120">Inserire il codice per recuperare il risultato dell'operazione nel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-120">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. <span data-ttu-id="45a7b-121">Implementare il metodo `TimeConsumingOperation`.</span><span class="sxs-lookup"><span data-stu-id="45a7b-121">Implement the `TimeConsumingOperation` method.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. <span data-ttu-id="45a7b-122">Nella Progettazione Windows Form fare doppio clic `startButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-122">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

11. <span data-ttu-id="45a7b-123">Chiamare il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento per `startButton` .</span><span class="sxs-lookup"><span data-stu-id="45a7b-123">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. <span data-ttu-id="45a7b-124">Nella Progettazione Windows Form fare doppio clic `cancelButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="45a7b-124">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

13. <span data-ttu-id="45a7b-125">Chiamare il <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodo nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento per `cancelButton` .</span><span class="sxs-lookup"><span data-stu-id="45a7b-125">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. <span data-ttu-id="45a7b-126">All'inizio del file importare gli spazi dei nomi System. ComponentModel e System. Threading.</span><span class="sxs-lookup"><span data-stu-id="45a7b-126">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. <span data-ttu-id="45a7b-127">Premere **F6** per compilare la soluzione, quindi premere **CTRL** + **F5** per eseguire l'applicazione all'esterno del debugger.</span><span class="sxs-lookup"><span data-stu-id="45a7b-127">Press **F6** to build the solution, and then press **Ctrl**+**F5** to run the application outside the debugger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45a7b-128">Se si preme **F5** per eseguire l'applicazione nel debugger, l'eccezione generata nel `TimeConsumingOperation` metodo viene rilevata e visualizzata dal debugger.</span><span class="sxs-lookup"><span data-stu-id="45a7b-128">If you press **F5** to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="45a7b-129">Quando si esegue l'applicazione all'esterno del debugger, <xref:System.ComponentModel.BackgroundWorker> gestisce l'eccezione e la memorizza nella cache nella <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> proprietà di <xref:System.ComponentModel.RunWorkerCompletedEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="45a7b-129">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>

16. <span data-ttu-id="45a7b-130">Fare clic sul pulsante **Start** per eseguire un'operazione asincrona, quindi fare clic sul pulsante **Annulla** per arrestare un'operazione asincrona in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45a7b-130">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>

     <span data-ttu-id="45a7b-131">Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="45a7b-131">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45a7b-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="45a7b-132">Next steps</span></span>

- <span data-ttu-id="45a7b-133">Implementare un modulo che segnala lo stato di avanzamento di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="45a7b-133">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="45a7b-134">Per altre informazioni, vedere [procedura: implementare un form che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="45a7b-134">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

- <span data-ttu-id="45a7b-135">Implementare una classe che supporta il modello asincrono per i componenti.</span><span class="sxs-lookup"><span data-stu-id="45a7b-135">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="45a7b-136">Per altre informazioni, vedere [implementazione del modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern).</span><span class="sxs-lookup"><span data-stu-id="45a7b-136">For more information, see [Implementing the Event-based Asynchronous Pattern](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern).</span></span>

## <a name="see-also"></a><span data-ttu-id="45a7b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45a7b-137">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="45a7b-138">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="45a7b-138">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="45a7b-139">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="45a7b-139">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="45a7b-140">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="45a7b-140">BackgroundWorker Component</span></span>](backgroundworker-component.md)
