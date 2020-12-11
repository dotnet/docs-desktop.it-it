---
title: 'Procedura: convalidare e unire PrintTicket'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968692"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="0b2e2-102">Procedura: convalidare e unire PrintTicket</span><span class="sxs-lookup"><span data-stu-id="0b2e2-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="0b2e2-103">Lo schema di [stampa](/windows/win32/printdocs/printschema) di Microsoft Windows include gli elementi e flessibili ed estendibili <xref:System.Printing.PrintCapabilities> <xref:System.Printing.PrintTicket> .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-103">The Microsoft Windows [Print Schema](/windows/win32/printdocs/printschema) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="0b2e2-104">Il primo rilevare le funzionalità di un dispositivo di stampa e il secondo specifica il modo in cui il dispositivo deve usare tali funzionalità rispetto a una particolare sequenza di documenti, documento singolo o singola pagina.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="0b2e2-105">Di seguito è riportata una sequenza di attività tipica per un'applicazione che supporta la stampa.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="0b2e2-106">Determinare le funzionalità di una stampante.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="0b2e2-107">Configurare <xref:System.Printing.PrintTicket> per usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="0b2e2-108">Convalidare l'oggetto <xref:System.Printing.PrintTicket> .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="0b2e2-109">Questo articolo illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b2e2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b2e2-110">Example</span></span>  
 <span data-ttu-id="0b2e2-111">Nell'esempio semplice riportato di seguito, si è interessati solo a se una stampante può supportare il duplexing, ovvero la stampa su due lati.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="0b2e2-112">I passaggi principali sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="0b2e2-113">Ottenere un <xref:System.Printing.PrintCapabilities> oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="0b2e2-114">Verificare la presenza delle funzionalità desiderate.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="0b2e2-115">Nell'esempio seguente viene testata la <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà dell' <xref:System.Printing.PrintCapabilities> oggetto per la presenza della funzionalità di stampa su entrambi i lati di un foglio di carta con la "trasformazione della pagina" lungo il lato lungo del foglio.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="0b2e2-116">Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, viene usato il `Contains` metodo di <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0b2e2-117">Questo passaggio non è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-117">This step is not strictly necessary.</span></span> <span data-ttu-id="0b2e2-118">Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo usato di seguito consente di controllare ogni richiesta in <xref:System.Printing.PrintTicket> rispetto alle funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="0b2e2-119">Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante sostituirà una richiesta alternativa nell'oggetto <xref:System.Printing.PrintTicket> restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="0b2e2-120">Se la stampante supporta la duplexing, il codice di esempio crea un oggetto <xref:System.Printing.PrintTicket> che richiede il duplexing.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="0b2e2-121">Tuttavia, l'applicazione non specifica ogni possibile impostazione della stampante disponibile nell' <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="0b2e2-122">Questo sarebbe uno spreco di tempo per programmatore e programma.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="0b2e2-123">Al contrario, il codice imposta solo la richiesta duplex, quindi unisce questo <xref:System.Printing.PrintTicket> oggetto a un oggetto esistente, completamente configurato e convalidato, <xref:System.Printing.PrintTicket> , in questo caso, il valore predefinito dell'utente <xref:System.Printing.PrintTicket> .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="0b2e2-124">Di conseguenza, l'esempio chiama il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo per unire il nuovo, minimo, <xref:System.Printing.PrintTicket> con il valore predefinito dell'utente <xref:System.Printing.PrintTicket> .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="0b2e2-125">Restituisce un oggetto <xref:System.Printing.ValidationResult> che include il nuovo oggetto <xref:System.Printing.PrintTicket> come una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="0b2e2-126">Nell'esempio viene quindi testato il nuovo <xref:System.Printing.PrintTicket> duplex delle richieste.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="0b2e2-127">In caso contrario, l'esempio lo rende il nuovo ticket di stampa predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="0b2e2-128">Se il passaggio 2 precedente era stato interrotto e la stampante non supportava il duplex lungo il lato lungo, il test avrebbe avuto esito `false` .</span><span class="sxs-lookup"><span data-stu-id="0b2e2-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="0b2e2-129">(Vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="0b2e2-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="0b2e2-130">L'ultimo passaggio significativo consiste nel eseguire il commit della modifica alla <xref:System.Printing.PrintQueue.UserPrintTicket%2A> proprietà di <xref:System.Printing.PrintQueue> con il <xref:System.Printing.PrintQueue.Commit%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="0b2e2-131">Per poter testare rapidamente questo esempio, il resto viene presentato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="0b2e2-132">Creare un progetto e uno spazio dei nomi e quindi incollare entrambi i frammenti di codice di questo articolo nel blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0b2e2-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="0b2e2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b2e2-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="0b2e2-134">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="0b2e2-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="0b2e2-135">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="0b2e2-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="0b2e2-136">Stampa schema</span><span class="sxs-lookup"><span data-stu-id="0b2e2-136">Print Schema</span></span>](/windows/win32/printdocs/printschema)
