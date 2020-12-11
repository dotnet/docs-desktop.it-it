---
title: 'Procedura: duplicare una stampante'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: e6af8d6410c4e383990bdaa27f97cc698be71719
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965794"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="fe1c0-102">Procedura: duplicare una stampante</span><span class="sxs-lookup"><span data-stu-id="fe1c0-102">How to: Clone a Printer</span></span>
<span data-ttu-id="fe1c0-103">La maggior parte delle aziende, a un certo punto, acquisterà più stampanti dello stesso modello.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="fe1c0-104">In genere, sono tutte installate con impostazioni di configurazione praticamente identiche.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="fe1c0-105">L'installazione di ogni stampante può richiedere molto tempo ed è soggetta a errori.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="fe1c0-106">Lo <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> spazio dei nomi e la <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposti con Microsoft .NET Framework permettono di installare immediatamente un numero qualsiasi di code di stampa aggiuntive clonate da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe1c0-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe1c0-107">Example</span></span>  
 <span data-ttu-id="fe1c0-108">Nell'esempio seguente viene clonata una seconda coda di stampa da una coda di stampa esistente.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="fe1c0-109">Il secondo è diverso dal primo solo per il nome, la posizione, la porta e lo stato condiviso.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="fe1c0-110">I passaggi principali per eseguire questa operazione sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="fe1c0-111">Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che verrà clonata.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="fe1c0-112">Creare un oggetto da dell'oggetto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> <xref:System.Printing.PrintQueue> .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="fe1c0-113">La <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty> .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="fe1c0-114">Esistono due modi per impostare il valore di una voce in questo dizionario.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="fe1c0-115">Usare i metodi **Remove** e del dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> per rimuovere la voce e quindi aggiungerla nuovamente con il valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="fe1c0-116">Usare il metodo del dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="fe1c0-117">Nell'esempio seguente vengono illustrate entrambe le modalità.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="fe1c0-118">Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto e impostarne il valore <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "transshared" e il relativo <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true` .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="fe1c0-119">Utilizzare l' <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto per essere il valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "transshared" di.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="fe1c0-120">Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto e impostarne <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "ShareName" e <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> su un oggetto appropriato <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="fe1c0-121">Usare l' <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "ShareName" di.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="fe1c0-122">Creare un altro <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto e impostarne il valore <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "location" e <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> su un oggetto appropriato <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="fe1c0-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="fe1c0-123">Utilizzare il secondo <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "location" di.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="fe1c0-124">Creare una matrice di <xref:System.String> s.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="fe1c0-125">Ogni elemento è il nome di una porta nel server.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="fe1c0-126">Utilizzare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="fe1c0-127">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="fe1c0-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="fe1c0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe1c0-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="fe1c0-129">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="fe1c0-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="fe1c0-130">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="fe1c0-130">Printing Overview</span></span>](printing-overview.md)
