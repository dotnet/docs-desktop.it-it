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
# <a name="how-to-validate-and-merge-printtickets"></a>Procedura: convalidare e unire PrintTicket
Lo schema di [stampa](/windows/win32/printdocs/printschema) di Microsoft Windows include gli elementi e flessibili ed estendibili <xref:System.Printing.PrintCapabilities> <xref:System.Printing.PrintTicket> . Il primo rilevare le funzionalità di un dispositivo di stampa e il secondo specifica il modo in cui il dispositivo deve usare tali funzionalità rispetto a una particolare sequenza di documenti, documento singolo o singola pagina.  
  
 Di seguito è riportata una sequenza di attività tipica per un'applicazione che supporta la stampa.  
  
1. Determinare le funzionalità di una stampante.  
  
2. Configurare <xref:System.Printing.PrintTicket> per usare tali funzionalità.  
  
3. Convalidare l'oggetto <xref:System.Printing.PrintTicket> .  
  
 Questo articolo illustra come eseguire questa operazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio semplice riportato di seguito, si è interessati solo a se una stampante può supportare il duplexing, ovvero la stampa su due lati. I passaggi principali sono i seguenti.  
  
1. Ottenere un <xref:System.Printing.PrintCapabilities> oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo.  
  
2. Verificare la presenza delle funzionalità desiderate. Nell'esempio seguente viene testata la <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà dell' <xref:System.Printing.PrintCapabilities> oggetto per la presenza della funzionalità di stampa su entrambi i lati di un foglio di carta con la "trasformazione della pagina" lungo il lato lungo del foglio. Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, viene usato il `Contains` metodo di <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> .  
  
    > [!NOTE]
    > Questo passaggio non è strettamente necessario. Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo usato di seguito consente di controllare ogni richiesta in <xref:System.Printing.PrintTicket> rispetto alle funzionalità della stampante. Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante sostituirà una richiesta alternativa nell'oggetto <xref:System.Printing.PrintTicket> restituito dal metodo.  
  
3. Se la stampante supporta la duplexing, il codice di esempio crea un oggetto <xref:System.Printing.PrintTicket> che richiede il duplexing. Tuttavia, l'applicazione non specifica ogni possibile impostazione della stampante disponibile nell' <xref:System.Printing.PrintTicket> elemento. Questo sarebbe uno spreco di tempo per programmatore e programma. Al contrario, il codice imposta solo la richiesta duplex, quindi unisce questo <xref:System.Printing.PrintTicket> oggetto a un oggetto esistente, completamente configurato e convalidato, <xref:System.Printing.PrintTicket> , in questo caso, il valore predefinito dell'utente <xref:System.Printing.PrintTicket> .  
  
4. Di conseguenza, l'esempio chiama il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo per unire il nuovo, minimo, <xref:System.Printing.PrintTicket> con il valore predefinito dell'utente <xref:System.Printing.PrintTicket> . Restituisce un oggetto <xref:System.Printing.ValidationResult> che include il nuovo oggetto <xref:System.Printing.PrintTicket> come una delle relative proprietà.  
  
5. Nell'esempio viene quindi testato il nuovo <xref:System.Printing.PrintTicket> duplex delle richieste. In caso contrario, l'esempio lo rende il nuovo ticket di stampa predefinito per l'utente. Se il passaggio 2 precedente era stato interrotto e la stampante non supportava il duplex lungo il lato lungo, il test avrebbe avuto esito `false` . (Vedere la nota precedente).  
  
6. L'ultimo passaggio significativo consiste nel eseguire il commit della modifica alla <xref:System.Printing.PrintQueue.UserPrintTicket%2A> proprietà di <xref:System.Printing.PrintQueue> con il <xref:System.Printing.PrintQueue.Commit%2A> metodo.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Per poter testare rapidamente questo esempio, il resto viene presentato di seguito. Creare un progetto e uno spazio dei nomi e quindi incollare entrambi i frammenti di codice di questo articolo nel blocco dello spazio dei nomi.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
- [Stampa schema](/windows/win32/printdocs/printschema)
