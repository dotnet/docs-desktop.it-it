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
# <a name="how-to-clone-a-printer"></a>Procedura: duplicare una stampante
La maggior parte delle aziende, a un certo punto, acquisterà più stampanti dello stesso modello. In genere, sono tutte installate con impostazioni di configurazione praticamente identiche. L'installazione di ogni stampante può richiedere molto tempo ed è soggetta a errori. Lo <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> spazio dei nomi e la <xref:System.Printing.PrintServer.InstallPrintQueue%2A> classe esposti con Microsoft .NET Framework permettono di installare immediatamente un numero qualsiasi di code di stampa aggiuntive clonate da una coda di stampa esistente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene clonata una seconda coda di stampa da una coda di stampa esistente. Il secondo è diverso dal primo solo per il nome, la posizione, la porta e lo stato condiviso. I passaggi principali per eseguire questa operazione sono i seguenti.  
  
1. Creare un <xref:System.Printing.PrintQueue> oggetto per la stampante esistente che verrà clonata.  
  
2. Creare un oggetto da dell'oggetto <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> <xref:System.Printing.PrintQueue> . La <xref:System.Collections.DictionaryEntry.Value%2A> proprietà di ogni voce in questo dizionario è un oggetto di uno dei tipi derivati da <xref:System.Printing.IndexedProperties.PrintProperty> . Esistono due modi per impostare il valore di una voce in questo dizionario.  
  
    - Usare i metodi **Remove** e del dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> per rimuovere la voce e quindi aggiungerla nuovamente con il valore desiderato.  
  
    - Usare il metodo del dizionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> .  
  
     Nell'esempio seguente vengono illustrate entrambe le modalità.  
  
3. Creare un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto e impostarne il valore <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "transshared" e il relativo <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true` .  
  
4. Utilizzare l' <xref:System.Printing.IndexedProperties.PrintBooleanProperty> oggetto per essere il valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "transshared" di.  
  
5. Creare un <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto e impostarne <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "ShareName" e <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> su un oggetto appropriato <xref:System.String> .  
  
6. Usare l' <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "ShareName" di.  
  
7. Creare un altro <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto e impostarne il valore <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> su "location" e <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> su un oggetto appropriato <xref:System.String> .  
  
8. Utilizzare il secondo <xref:System.Printing.IndexedProperties.PrintStringProperty> oggetto come valore della <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> voce "location" di.  
  
9. Creare una matrice di <xref:System.String> s. Ogni elemento è il nome di una porta nel server.  
  
10. Utilizzare <xref:System.Printing.PrintServer.InstallPrintQueue%2A> per installare la nuova stampante con i nuovi valori.  
  
 Di seguito è riportato un esempio.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sulla stampa](printing-overview.md)
