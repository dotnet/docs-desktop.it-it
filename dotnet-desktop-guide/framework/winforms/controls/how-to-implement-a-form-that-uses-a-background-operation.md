---
title: "Procedura: Implementare un modulo che usa un'operazione in background"
description: Informazioni su come implementare un Windows Form che usa un'operazione in background in modo che un'operazione possa continuare a essere eseguita mentre un'altra operazione continua.
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
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 85a583ce81c8d7e169302dd9e3e304c22977327a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964342"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="3c330-103">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="3c330-103">How to: Implement a Form That Uses a Background Operation</span></span>

<span data-ttu-id="3c330-104">Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="3c330-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="3c330-105">Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="3c330-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="3c330-106">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="3c330-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="3c330-107">Vedere anche [Procedura dettagliata: implementazione di un modulo che usa un'operazione in background](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="3c330-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c330-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c330-108">Example</span></span>  

 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c330-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3c330-109">Compiling the Code</span></span>  

 <span data-ttu-id="3c330-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c330-110">This example requires:</span></span>  
  
- <span data-ttu-id="3c330-111">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3c330-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3c330-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="3c330-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="3c330-113">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="3c330-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="3c330-114">Vedere [Procedure consigliate per l'uso del threading gestito](/dotnet/standard/threading/managed-threading-best-practices) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="3c330-114">Consult the [Managed Threading Best Practices](/dotnet/standard/threading/managed-threading-best-practices) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c330-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c330-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="3c330-116">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="3c330-116">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [<span data-ttu-id="3c330-117">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="3c330-117">Managed Threading Best Practices</span></span>](/dotnet/standard/threading/managed-threading-best-practices)
