---
title: Multithreading nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961504"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="85d7c-102">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="85d7c-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="85d7c-103">In molte applicazioni è possibile rendere più reattive l'interfaccia utente eseguendo operazioni che richiedono molto tempo in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="85d7c-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="85d7c-104">Sono disponibili diversi strumenti per il multithreading dei controlli di Windows Forms, tra cui lo <xref:System.Threading> spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo e il `BackgroundWorker` componente.</span><span class="sxs-lookup"><span data-stu-id="85d7c-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85d7c-105">Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità allo <xref:System.Threading> spazio dei nomi e al <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo. questi elementi vengono tuttavia conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="85d7c-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="85d7c-106">Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85d7c-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85d7c-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="85d7c-107">In This Section</span></span>  
 [<span data-ttu-id="85d7c-108">Procedura: Effettuare chiamate thread-safe ai controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85d7c-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="85d7c-109">Viene illustrato come eseguire chiamate thread-safe a controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="85d7c-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="85d7c-110">Procedura: Usare un thread in background per la ricerca di file</span><span class="sxs-lookup"><span data-stu-id="85d7c-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="85d7c-111">Viene illustrato come utilizzare lo <xref:System.Threading> spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="85d7c-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="85d7c-112">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="85d7c-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="85d7c-113">Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="85d7c-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="85d7c-114">Documenta come caricare un suono in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="85d7c-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="85d7c-115">Documenta come caricare un'immagine in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="85d7c-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="85d7c-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="85d7c-116">Related Sections</span></span>  
 [<span data-ttu-id="85d7c-117">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="85d7c-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="85d7c-118">Viene illustrato come eseguire un'operazione che richiede molto tempo con il <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="85d7c-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="85d7c-119">Cenni preliminari sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="85d7c-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="85d7c-120">Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="85d7c-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
