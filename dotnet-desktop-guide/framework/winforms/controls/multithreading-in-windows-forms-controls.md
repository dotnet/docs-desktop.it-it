---
title: Multithreading nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961504"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading nei controlli Windows Form
In molte applicazioni è possibile rendere più reattive l'interfaccia utente eseguendo operazioni che richiedono molto tempo in un altro thread. Sono disponibili diversi strumenti per il multithreading dei controlli di Windows Forms, tra cui lo <xref:System.Threading> spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo e il `BackgroundWorker` componente.  
  
> [!NOTE]
> Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità allo <xref:System.Threading> spazio dei nomi e al <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo. questi elementi vengono tuttavia conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie. Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Effettuare chiamate thread-safe ai controlli di Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Viene illustrato come eseguire chiamate thread-safe a controlli Windows Forms.  
  
 [Procedura: Usare un thread in background per la ricerca di file](how-to-use-a-background-thread-to-search-for-files.md)  
 Viene illustrato come utilizzare lo <xref:System.Threading> spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta come caricare un suono in modo asincrono.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta come caricare un'immagine in modo asincrono.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come eseguire un'operazione che richiede molto tempo con il <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.
