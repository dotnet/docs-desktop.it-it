---
title: Cenni preliminari sul componente BackgroundWorker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: ba197331863b1b6dd49fbb26249bfd4a46106e34
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962239"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="7c08c-102">Cenni preliminari sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="7c08c-102">BackgroundWorker Component Overview</span></span>

<span data-ttu-id="7c08c-103">Molte operazioni comuni hanno tempi di esecuzione particolarmente lunghi,</span><span class="sxs-lookup"><span data-stu-id="7c08c-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="7c08c-104">Esempio:</span><span class="sxs-lookup"><span data-stu-id="7c08c-104">For example:</span></span>  
  
- <span data-ttu-id="7c08c-105">Download di immagini</span><span class="sxs-lookup"><span data-stu-id="7c08c-105">Image downloads</span></span>  
  
- <span data-ttu-id="7c08c-106">Chiamate di servizi Web</span><span class="sxs-lookup"><span data-stu-id="7c08c-106">Web service invocations</span></span>  
  
- <span data-ttu-id="7c08c-107">Download e caricamento di file (anche per applicazioni peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="7c08c-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
- <span data-ttu-id="7c08c-108">Calcoli locali complessi</span><span class="sxs-lookup"><span data-stu-id="7c08c-108">Complex local computations</span></span>  
  
- <span data-ttu-id="7c08c-109">Transazioni di database</span><span class="sxs-lookup"><span data-stu-id="7c08c-109">Database transactions</span></span>  
  
- <span data-ttu-id="7c08c-110">Accesso locale ai dischi, a causa della velocità ridotta rispetto all'accesso alla memoria</span><span class="sxs-lookup"><span data-stu-id="7c08c-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="7c08c-111">Operazioni come queste possono causare il blocco dell'interfaccia utente mentre sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c08c-111">Operations like these can cause your user interface to block while they are running.</span></span> <span data-ttu-id="7c08c-112">Nel caso sia necessario eseguire operazioni di questo genere ma si vogliano evitare ritardi di risposta dell'interfaccia utente, il componente <xref:System.ComponentModel.BackgroundWorker> costituisce la soluzione ideale.</span><span class="sxs-lookup"><span data-stu-id="7c08c-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="7c08c-113">Il componente <xref:System.ComponentModel.BackgroundWorker> offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono (in background) su un thread diverso da quello usato dall'interfaccia utente principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c08c-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="7c08c-114">Per usare un componente <xref:System.ComponentModel.BackgroundWorker>, è sufficiente indicare il metodo di lavoro da eseguire in background e quindi chiamare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c08c-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="7c08c-115">Il thread chiamante continua l'esecuzione normale mentre il metodo di lavoro viene eseguito in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="7c08c-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="7c08c-116">Al completamento dell'esecuzione del metodo, il componente <xref:System.ComponentModel.BackgroundWorker> avvisa il thread chiamante attivando l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, in cui è possibile includere i risultati dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="7c08c-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="7c08c-117">Il <xref:System.ComponentModel.BackgroundWorker> componente è disponibile nella scheda **componenti** della **casella degli strumenti**. Per aggiungere un oggetto <xref:System.ComponentModel.BackgroundWorker> al form, trascinare il <xref:System.ComponentModel.BackgroundWorker> componente nel form.</span><span class="sxs-lookup"><span data-stu-id="7c08c-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="7c08c-118">Viene visualizzato nella barra dei componenti e le relative proprietà vengono visualizzate nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="7c08c-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="7c08c-119">Per avviare l'operazione asincrona, usare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c08c-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="7c08c-120">Il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> accetta un parametro `object` facoltativo, che può essere usato per passare gli argomenti al metodo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7c08c-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="7c08c-121">La classe <xref:System.ComponentModel.BackgroundWorker> espone l'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> a cui viene collegato il thread di lavoro mediante un gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="7c08c-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="7c08c-122">Il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> accetta un parametro <xref:System.ComponentModel.DoWorkEventArgs> che include una proprietà <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c08c-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="7c08c-123">Questa proprietà riceve il parametro da <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e può essere passata al metodo di lavoro, che verrà chiamato nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="7c08c-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="7c08c-124">L'esempio seguente illustra come assegnare un risultato proveniente da un metodo di lavoro denominato `ComputeFibonacci`.</span><span class="sxs-lookup"><span data-stu-id="7c08c-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="7c08c-125">Fa parte di un esempio più ampio, che è possibile trovare in [procedura: implementare un form che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="7c08c-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="7c08c-126">Per altre informazioni sull'uso dei gestori eventi, vedere [eventi](/dotnet/standard/events/index).</span><span class="sxs-lookup"><span data-stu-id="7c08c-126">For more information on using event handlers, see [Events](/dotnet/standard/events/index).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7c08c-127">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="7c08c-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="7c08c-128">Vedere [Procedure consigliate per l'uso del threading gestito](/dotnet/standard/threading/managed-threading-best-practices) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="7c08c-128">Consult the [Managed Threading Best Practices](/dotnet/standard/threading/managed-threading-best-practices) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="7c08c-129">Per altre informazioni sull'uso della <xref:System.ComponentModel.BackgroundWorker> classe, vedere [procedura: eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="7c08c-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c08c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c08c-130">See also</span></span>

- [<span data-ttu-id="7c08c-131">Threading gestito</span><span class="sxs-lookup"><span data-stu-id="7c08c-131">Managed Threading</span></span>](/dotnet/standard/threading/index)
- [<span data-ttu-id="7c08c-132">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="7c08c-132">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [<span data-ttu-id="7c08c-133">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="7c08c-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
