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
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Procedura: ottenere le proprietà di un oggetto di sistema di stampa senza ricorrere alla reflection
L'uso della reflection per descrivere le proprietà (e i tipi di tali proprietà) su un oggetto può rallentare le prestazioni dell'applicazione. Lo <xref:System.Printing.IndexedProperties> spazio dei nomi fornisce un mezzo per ottenere queste informazioni usando la reflection.  
  
## <a name="example"></a>Esempio  
 Di seguito sono riportati i passaggi per eseguire questa operazione.  
  
1. Creare un'istanza del tipo. Nell'esempio seguente, il tipo è il <xref:System.Printing.PrintQueue> tipo fornito con Microsoft .NET Framework, ma il codice quasi identico dovrebbe funzionare per i tipi che si derivano da <xref:System.Printing.PrintSystemObject> .  
  
2. Creare un oggetto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> dall'oggetto del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> . La <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty> .  
  
3. Enumerare i membri del dizionario. Per ognuno di essi, eseguire le operazioni seguenti.  
  
4. Eseguire il cast del valore di ogni voce in <xref:System.Printing.IndexedProperties.PrintProperty> e usarlo per creare un <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.  
  
5. Ottiene il tipo di <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> di ogni <xref:System.Printing.IndexedProperties.PrintProperty> oggetto.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
