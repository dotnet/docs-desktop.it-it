---
title: 'Procedura: enumerare un sottoinsieme di code di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967765"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Procedura: enumerare un sottoinsieme di code di stampa
Una situazione comune affrontata dai professionisti IT (Information Technology) che gestiscono un set di stampanti a livello aziendale consiste nel generare un elenco di stampanti con determinate caratteristiche. Questa funzionalità viene fornita dal <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e dall' <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare. In questo esempio, si stanno cercando le code di stampa installate localmente nel server di stampa e condivise. L' <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione offre molte altre possibilità.  
  
 Il codice crea quindi un <xref:System.Printing.LocalPrintServer> oggetto, una classe derivata da <xref:System.Printing.PrintServer> . Il server di stampa locale è il computer in cui è in esecuzione l'applicazione.  
  
 L'ultimo passaggio significativo consiste nel passare la matrice al <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Questo esempio può essere esteso facendo in modo `foreach` che il ciclo che scorre ogni coda di stampa esegua ulteriormente lo screening. Ad esempio, è possibile escludere le stampanti che non supportano la stampa su due lati, facendo in modo che il ciclo chiami il metodo di ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> e testando il valore restituito per la presenza di duplex.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
- [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer)
