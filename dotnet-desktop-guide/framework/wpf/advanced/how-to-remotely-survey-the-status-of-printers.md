---
title: 'Procedura: verificare lo stato delle stampanti da postazione remota'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 94390b0660afce6af38c7ed6da6174f5425802c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962791"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="6e699-102">Procedura: verificare lo stato delle stampanti da postazione remota</span><span class="sxs-lookup"><span data-stu-id="6e699-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="6e699-103">In qualsiasi momento in aziende di medie e grandi dimensioni potrebbero essere presenti più stampanti non funzionanti a causa di fogli bloccati o carta esaurita o un'altra situazione problematica.</span><span class="sxs-lookup"><span data-stu-id="6e699-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="6e699-104">Il set completo di proprietà della stampante esposte nelle API di Microsoft .NET Framework fornisce un mezzo per eseguire un rapido sondaggio degli Stati delle stampanti.</span><span class="sxs-lookup"><span data-stu-id="6e699-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e699-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e699-105">Example</span></span>  
 <span data-ttu-id="6e699-106">Di seguito sono indicati i passaggi principali per la creazione di questo tipo di utilità.</span><span class="sxs-lookup"><span data-stu-id="6e699-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="6e699-107">Ottenere un elenco di tutti i server di stampa.</span><span class="sxs-lookup"><span data-stu-id="6e699-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="6e699-108">Riprodurre il ciclo dei server per eseguire una query sulle code di stampa.</span><span class="sxs-lookup"><span data-stu-id="6e699-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="6e699-109">In ogni passaggio del ciclo del server, scorrere tutte le code del server e leggere tutte le proprietà che potrebbero indicare che la coda attualmente non funziona.</span><span class="sxs-lookup"><span data-stu-id="6e699-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="6e699-110">Il codice seguente è una serie di frammenti di codice.</span><span class="sxs-lookup"><span data-stu-id="6e699-110">The code below is a series of snippets.</span></span> <span data-ttu-id="6e699-111">Per semplicità, in questo esempio si presuppone che esista un elenco delimitato da CRLF di server di stampa.</span><span class="sxs-lookup"><span data-stu-id="6e699-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="6e699-112">La variabile `fileOfPrintServers` è un <xref:System.IO.StreamReader> oggetto per il file.</span><span class="sxs-lookup"><span data-stu-id="6e699-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="6e699-113">Poiché ogni nome di server si trova su una riga a se stante, qualsiasi chiamata di <xref:System.IO.StreamReader.ReadLine%2A> ottiene il nome del server successivo e sposta il <xref:System.IO.StreamReader> cursore all'inizio della riga successiva.</span><span class="sxs-lookup"><span data-stu-id="6e699-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="6e699-114">All'interno del ciclo esterno, il codice crea un <xref:System.Printing.PrintServer> oggetto per il server di stampa più recente e specifica che l'applicazione deve disporre di diritti amministrativi per il server.</span><span class="sxs-lookup"><span data-stu-id="6e699-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e699-115">Se sono presenti numerosi server, è possibile migliorare le prestazioni usando i <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> costruttori che inizializzano solo le proprietà necessarie.</span><span class="sxs-lookup"><span data-stu-id="6e699-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="6e699-116">Nell'esempio viene quindi usato <xref:System.Printing.PrintServer.GetPrintQueues%2A> per creare una raccolta di tutte le code del server e iniziare a scorrerle.</span><span class="sxs-lookup"><span data-stu-id="6e699-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="6e699-117">Il ciclo interno include una struttura ramificata corrispondente ai due metodi di verifica dello stato della stampante:</span><span class="sxs-lookup"><span data-stu-id="6e699-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="6e699-118">È possibile leggere i flag della <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà che è di tipo <xref:System.Printing.PrintQueueStatus> .</span><span class="sxs-lookup"><span data-stu-id="6e699-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="6e699-119">È possibile leggere tutte le proprietà rilevanti, ad esempio <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> , e <xref:System.Printing.PrintQueue.IsPaperJammed%2A> .</span><span class="sxs-lookup"><span data-stu-id="6e699-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="6e699-120">Questo esempio illustra entrambi i metodi, quindi all'utente è stato chiesto in precedenza come metodo da usare e ha risposto con "y" se volevano usare i flag della <xref:System.Printing.PrintQueue.QueueStatus%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e699-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if they wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="6e699-121">Per i dettagli dei due metodi, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="6e699-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="6e699-122">Infine, i risultati vengono presentati all'utente.</span><span class="sxs-lookup"><span data-stu-id="6e699-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="6e699-123">Per controllare lo stato della stampante usando i flag della <xref:System.Printing.PrintQueue.QueueStatus%2A> proprietà, controllare ogni flag pertinente per verificare se è impostato.</span><span class="sxs-lookup"><span data-stu-id="6e699-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="6e699-124">Il metodo standard per verificare se un bit è impostato in un set di flag di bit consiste nell'eseguire un'operazione di AND logico con il set di flag come uno degli operandi e il flag stesso come altro operando.</span><span class="sxs-lookup"><span data-stu-id="6e699-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="6e699-125">Poiché il flag stesso ha un solo bit impostato, il risultato dell'AND logico è che, al massimo, è impostato quello stesso bit.</span><span class="sxs-lookup"><span data-stu-id="6e699-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="6e699-126">Per verificare se lo è o meno, confrontare il risultato dell’AND logico con il flag stesso.</span><span class="sxs-lookup"><span data-stu-id="6e699-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="6e699-127">Per ulteriori informazioni, vedere <xref:System.Printing.PrintQueueStatus> l' [ operatore& (riferimenti per C#)](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)e <xref:System.FlagsAttribute> .</span><span class="sxs-lookup"><span data-stu-id="6e699-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="6e699-128">Per ogni attributo il cui bit è impostato, il codice aggiunge un avviso al report finale che verrà presentato all'utente.</span><span class="sxs-lookup"><span data-stu-id="6e699-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="6e699-129">(Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)</span><span class="sxs-lookup"><span data-stu-id="6e699-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="6e699-130">Per controllare lo stato delle stampanti usando tutte le proprietà, basta leggere tutte le proprietà e aggiungere una nota alla relazione finale che sarà presentata all'utente se la proprietà è `true`.</span><span class="sxs-lookup"><span data-stu-id="6e699-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="6e699-131">(Il metodo **ReportAvailabilityAtThisTime** che viene chiamato alla fine del codice è illustrato di seguito.)</span><span class="sxs-lookup"><span data-stu-id="6e699-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="6e699-132">Il metodo **ReportAvailabilityAtThisTime** è stato creato nel caso in cui sia necessario determinare se la coda è disponibile in quel momento preciso del giorno.</span><span class="sxs-lookup"><span data-stu-id="6e699-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="6e699-133">Il metodo non eseguirà alcuna operazione se le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> proprietà e sono uguali; in tal caso, la stampante è sempre disponibile.</span><span class="sxs-lookup"><span data-stu-id="6e699-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="6e699-134">Se sono diversi, il metodo ottiene l'ora corrente che deve quindi essere convertita in minuti totali dopo la mezzanotte perché le <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> proprietà e sono <xref:System.Int32> rappresentate da minuti, dopo la mezzanotte, non da <xref:System.DateTime> oggetti.</span><span class="sxs-lookup"><span data-stu-id="6e699-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="6e699-135">Infine, il metodo controlla se l'ora corrente è compresa tra l'inizio e il lasso di tempo "fino a".</span><span class="sxs-lookup"><span data-stu-id="6e699-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="6e699-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e699-136">See also</span></span>

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [<span data-ttu-id="6e699-137"> Operatore& (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6e699-137">& Operator (C# Reference)</span></span>](/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-)
- [<span data-ttu-id="6e699-138">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="6e699-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="6e699-139">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="6e699-139">Printing Overview</span></span>](printing-overview.md)
