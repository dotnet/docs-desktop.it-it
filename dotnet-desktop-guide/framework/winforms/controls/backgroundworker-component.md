---
title: Componente BackgroundWorker
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 6a059a9d1eaf2238f21675fec5dc0329a1c714fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952649"
---
# <a name="backgroundworker-component"></a>Componente BackgroundWorker

Il `BackgroundWorker` componente consente al form o al controllo di eseguire un'operazione in modo asincrono.  
  
## <a name="in-this-section"></a>Contenuto della sezione  

 [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Descrive il `BackgroundWorker` componente, che offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono ("in background"), su un thread diverso dal thread principale dell'interfaccia utente dell'applicazione.  
  
 [Procedura dettagliata: Esecuzione di un'operazione in background](walkthrough-running-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione dispendiosa in termini di tempo in un thread separato.  
  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per eseguire un'operazione dispendiosa in termini di tempo in un thread separato.  
  
 [Procedura dettagliata: Implementazione di un modulo che usa un'operazione in background](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione utilizzando la finestra di progettazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Scaricare un file in background](how-to-download-a-file-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.  
  
## <a name="reference"></a>Informazioni di riferimento  

 <xref:System.ComponentModel.BackgroundWorker>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Descrive il tipo che contiene i dati per l' <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Descrive il tipo che contiene i dati per l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.  
  
## <a name="related-sections"></a>Sezioni correlate  

 [Cenni preliminari sul modello asincrono basato su eventi](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)  
 Viene descritto il modo in cui il modello asincrono rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi inerenti alla progettazione multithreading.
