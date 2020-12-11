---
title: Cenni preliminari sul componente BackgroundWorker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: ba197331863b1b6dd49fbb26249bfd4a46106e34
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962239"
---
# <a name="backgroundworker-component-overview"></a>Cenni preliminari sul componente BackgroundWorker

Molte operazioni comuni hanno tempi di esecuzione particolarmente lunghi, Esempio:  
  
- Download di immagini  
  
- Chiamate di servizi Web  
  
- Download e caricamento di file (anche per applicazioni peer-to-peer)  
  
- Calcoli locali complessi  
  
- Transazioni di database  
  
- Accesso locale ai dischi, a causa della velocità ridotta rispetto all'accesso alla memoria  
  
 Operazioni come queste possono causare il blocco dell'interfaccia utente mentre sono in esecuzione. Nel caso sia necessario eseguire operazioni di questo genere ma si vogliano evitare ritardi di risposta dell'interfaccia utente, il componente <xref:System.ComponentModel.BackgroundWorker> costituisce la soluzione ideale.  
  
 Il componente <xref:System.ComponentModel.BackgroundWorker> offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono (in background) su un thread diverso da quello usato dall'interfaccia utente principale dell'applicazione. Per usare un componente <xref:System.ComponentModel.BackgroundWorker>, è sufficiente indicare il metodo di lavoro da eseguire in background e quindi chiamare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. Il thread chiamante continua l'esecuzione normale mentre il metodo di lavoro viene eseguito in modo asincrono. Al completamento dell'esecuzione del metodo, il componente <xref:System.ComponentModel.BackgroundWorker> avvisa il thread chiamante attivando l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, in cui è possibile includere i risultati dell'operazione.  
  
 Il <xref:System.ComponentModel.BackgroundWorker> componente è disponibile nella scheda **componenti** della **casella degli strumenti**. Per aggiungere un oggetto <xref:System.ComponentModel.BackgroundWorker> al form, trascinare il <xref:System.ComponentModel.BackgroundWorker> componente nel form. Viene visualizzato nella barra dei componenti e le relative proprietà vengono visualizzate nella finestra **Proprietà** .  
  
 Per avviare l'operazione asincrona, usare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. Il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> accetta un parametro `object` facoltativo, che può essere usato per passare gli argomenti al metodo di lavoro. La classe <xref:System.ComponentModel.BackgroundWorker> espone l'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> a cui viene collegato il thread di lavoro mediante un gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
 Il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> accetta un parametro <xref:System.ComponentModel.DoWorkEventArgs> che include una proprietà <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>. Questa proprietà riceve il parametro da <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e può essere passata al metodo di lavoro, che verrà chiamato nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>. L'esempio seguente illustra come assegnare un risultato proveniente da un metodo di lavoro denominato `ComputeFibonacci`. Fa parte di un esempio più ampio, che è possibile trovare in [procedura: implementare un form che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md).  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Per altre informazioni sull'uso dei gestori eventi, vedere [eventi](/dotnet/standard/events/index).  
  
> [!CAUTION]
> L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi. Vedere [Procedure consigliate per l'uso del threading gestito](/dotnet/standard/threading/managed-threading-best-practices) prima di implementare soluzioni che usano il multithreading.  
  
 Per altre informazioni sull'uso della <xref:System.ComponentModel.BackgroundWorker> classe, vedere [procedura: eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).  
  
## <a name="see-also"></a>Vedere anche

- [Threading gestito](/dotnet/standard/threading/index)
- [Cenni preliminari sul modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
