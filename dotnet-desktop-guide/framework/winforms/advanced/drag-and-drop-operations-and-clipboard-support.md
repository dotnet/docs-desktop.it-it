---
title: Supporto delle operazioni di trascinamento della selezione e degli Appunti
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 5e7bb75b648163dab7e410a159d55ebbb75f1b0a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952463"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="c7b98-102">Supporto delle operazioni di trascinamento della selezione e degli Appunti</span><span class="sxs-lookup"><span data-stu-id="c7b98-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="c7b98-103">È possibile abilitare le operazioni di trascinamento all'interno di applicazioni per Windows mediante la gestione di una serie di eventi, in particolare gli eventi <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> e <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="c7b98-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="c7b98-104">È anche possibile implementare il supporto per operazioni di taglia/copia/incolla e il trasferimento di dati dell'utente negli Appunti all'interno delle applicazioni basate su Windows usando semplici chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="c7b98-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7b98-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c7b98-105">In This Section</span></span>  
 [<span data-ttu-id="c7b98-106">Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7b98-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="c7b98-107">Illustra come avviare un'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="c7b98-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="c7b98-108">Procedura: Eseguire operazioni di trascinamento della selezione tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="c7b98-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="c7b98-109">Illustra come eseguire le operazioni di trascinamento e rilascio tra le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c7b98-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="c7b98-110">Procedura: Aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="c7b98-110">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="c7b98-111">Descrive un modo per inserire informazioni negli Appunti a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="c7b98-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="c7b98-112">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="c7b98-112">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="c7b98-113">Descrive come accedere ai dati archiviati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="c7b98-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7b98-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c7b98-114">Related Sections</span></span>  
 [<span data-ttu-id="c7b98-115">Funzionalità di trascinamento della selezione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7b98-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="c7b98-116">Descrive i metodi, gli eventi e le classi usate per implementare il comportamento di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="c7b98-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="c7b98-117">Descrive gli aspetti complessi relativi all'evento che richiede l'autorizzazione per proseguire con l'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c7b98-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="c7b98-118">Descrive gli aspetti complessi relativi al metodo fondamentale per l'inizio dell'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c7b98-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="c7b98-119">Vedere anche [procedura: inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="c7b98-119">Also see [How to: Send Data to the Active MDI Child](how-to-send-data-to-the-active-mdi-child.md).</span></span>
