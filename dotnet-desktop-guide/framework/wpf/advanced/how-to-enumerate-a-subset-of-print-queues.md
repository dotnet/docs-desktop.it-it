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
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="f0e88-102">Procedura: enumerare un sottoinsieme di code di stampa</span><span class="sxs-lookup"><span data-stu-id="f0e88-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="f0e88-103">Una situazione comune affrontata dai professionisti IT (Information Technology) che gestiscono un set di stampanti a livello aziendale consiste nel generare un elenco di stampanti con determinate caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="f0e88-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="f0e88-104">Questa funzionalità viene fornita dal <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e dall' <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0e88-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0e88-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0e88-105">Example</span></span>  
 <span data-ttu-id="f0e88-106">Nell'esempio seguente il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare.</span><span class="sxs-lookup"><span data-stu-id="f0e88-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="f0e88-107">In questo esempio, si stanno cercando le code di stampa installate localmente nel server di stampa e condivise.</span><span class="sxs-lookup"><span data-stu-id="f0e88-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="f0e88-108">L' <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione offre molte altre possibilità.</span><span class="sxs-lookup"><span data-stu-id="f0e88-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="f0e88-109">Il codice crea quindi un <xref:System.Printing.LocalPrintServer> oggetto, una classe derivata da <xref:System.Printing.PrintServer> .</span><span class="sxs-lookup"><span data-stu-id="f0e88-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="f0e88-110">Il server di stampa locale è il computer in cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0e88-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="f0e88-111">L'ultimo passaggio significativo consiste nel passare la matrice al <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f0e88-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="f0e88-112">Infine, i risultati vengono presentati all'utente.</span><span class="sxs-lookup"><span data-stu-id="f0e88-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="f0e88-113">Questo esempio può essere esteso facendo in modo `foreach` che il ciclo che scorre ogni coda di stampa esegua ulteriormente lo screening.</span><span class="sxs-lookup"><span data-stu-id="f0e88-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="f0e88-114">Ad esempio, è possibile escludere le stampanti che non supportano la stampa su due lati, facendo in modo che il ciclo chiami il metodo di ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> e testando il valore restituito per la presenza di duplex.</span><span class="sxs-lookup"><span data-stu-id="f0e88-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e88-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0e88-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="f0e88-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="f0e88-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="f0e88-117">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="f0e88-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="f0e88-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="f0e88-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
