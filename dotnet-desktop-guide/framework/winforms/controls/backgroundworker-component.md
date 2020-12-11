---
title: Componente BackgroundWorker
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 6a059a9d1eaf2238f21675fec5dc0329a1c714fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952649"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="46d2c-102">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="46d2c-102">BackgroundWorker Component</span></span>

<span data-ttu-id="46d2c-103">Il `BackgroundWorker` componente consente al form o al controllo di eseguire un'operazione in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="46d2c-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46d2c-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="46d2c-104">In This Section</span></span>  

 [<span data-ttu-id="46d2c-105">Cenni preliminari sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="46d2c-105">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="46d2c-106">Descrive il `BackgroundWorker` componente, che offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono ("in background"), su un thread diverso dal thread principale dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="46d2c-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="46d2c-107">Procedura dettagliata: Esecuzione di un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="46d2c-107">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="46d2c-108">Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione dispendiosa in termini di tempo in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="46d2c-109">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="46d2c-109">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="46d2c-110">Viene illustrato come utilizzare il `BackgroundWorker` componente per eseguire un'operazione dispendiosa in termini di tempo in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="46d2c-111">Procedura dettagliata: Implementazione di un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="46d2c-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="46d2c-112">Crea un'applicazione utilizzando la finestra di progettazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="46d2c-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="46d2c-113">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="46d2c-113">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="46d2c-114">Crea un'applicazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="46d2c-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="46d2c-115">Procedura: Scaricare un file in background</span><span class="sxs-lookup"><span data-stu-id="46d2c-115">How to: Download a File in the Background</span></span>](how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="46d2c-116">Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="46d2c-117">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="46d2c-117">Reference</span></span>  

 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="46d2c-118">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="46d2c-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="46d2c-119">Descrive il tipo che contiene i dati per l' <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="46d2c-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="46d2c-120">Descrive il tipo che contiene i dati per l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="46d2c-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46d2c-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="46d2c-121">Related Sections</span></span>  

 [<span data-ttu-id="46d2c-122">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="46d2c-122">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)  
 <span data-ttu-id="46d2c-123">Viene descritto il modo in cui il modello asincrono rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi inerenti alla progettazione multithreading.</span><span class="sxs-lookup"><span data-stu-id="46d2c-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
