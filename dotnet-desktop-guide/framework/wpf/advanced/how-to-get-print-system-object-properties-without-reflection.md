---
title: 'Procedura: ottenere le proprietà di un oggetto di sistema di stampa senza ricorrere alla reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: bb906dafd98e75708764b5f0f009900719f6a475
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963769"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="7e36d-102">Procedura: ottenere le proprietà di un oggetto di sistema di stampa senza ricorrere alla reflection</span><span class="sxs-lookup"><span data-stu-id="7e36d-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="7e36d-103">L'uso della reflection per descrivere le proprietà (e i tipi di tali proprietà) su un oggetto può rallentare le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7e36d-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="7e36d-104">Lo <xref:System.Printing.IndexedProperties> spazio dei nomi fornisce un mezzo per ottenere queste informazioni usando la reflection.</span><span class="sxs-lookup"><span data-stu-id="7e36d-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e36d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e36d-105">Example</span></span>  
 <span data-ttu-id="7e36d-106">Di seguito sono riportati i passaggi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="7e36d-106">The steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="7e36d-107">Creare un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="7e36d-107">Create an instance of the type.</span></span> <span data-ttu-id="7e36d-108">Nell'esempio seguente, il tipo è il <xref:System.Printing.PrintQueue> tipo fornito con Microsoft .NET Framework, ma il codice quasi identico dovrebbe funzionare per i tipi che si derivano da <xref:System.Printing.PrintSystemObject> .</span><span class="sxs-lookup"><span data-stu-id="7e36d-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2. <span data-ttu-id="7e36d-109">Creare un oggetto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dall'oggetto del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> .</span><span class="sxs-lookup"><span data-stu-id="7e36d-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="7e36d-110">La <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty> .</span><span class="sxs-lookup"><span data-stu-id="7e36d-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3. <span data-ttu-id="7e36d-111">Enumerare i membri del dizionario.</span><span class="sxs-lookup"><span data-stu-id="7e36d-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="7e36d-112">Per ognuno di essi, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7e36d-112">For each of them, do the following.</span></span>  
  
4. <span data-ttu-id="7e36d-113">Eseguire il cast del valore di ogni voce in <xref:System.Printing.IndexedProperties.PrintProperty> e usarlo per creare un <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e36d-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5. <span data-ttu-id="7e36d-114">Ottiene il tipo di <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> di ogni <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e36d-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="7e36d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e36d-115">See also</span></span>

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="7e36d-116">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="7e36d-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7e36d-117">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="7e36d-117">Printing Overview</span></span>](printing-overview.md)
