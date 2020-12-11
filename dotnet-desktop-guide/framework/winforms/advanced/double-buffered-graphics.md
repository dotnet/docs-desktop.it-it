---
title: Grafica a doppio buffer
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: 20ec03e6b84110f7ea00c134dc18b23f233c5f58
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960982"
---
# <a name="double-buffered-graphics"></a>Grafica a doppio buffer
Lo sfarfallio è un problema comune della programmazione della grafica. Le operazioni di grafica che richiedono più operazioni complesse di disegno possono causare lo sfarfallio o altri gravi problemi delle immagini sottoposte a rendering. Per risolvere questi problemi, .NET Framework fornisce l'accesso al doppio buffer.  
  
 Il doppio buffer usa un buffer di memoria per risolvere i problemi di sfarfallio associati a più operazioni di disegno. Quando il doppio buffer è abilitato, tutte le operazioni di disegno vengono prima sottoposte a rendering in un buffer di memoria invece che nella superficie di disegno visualizzata. Dopo che tutte le operazioni di disegno sono state completate, il buffer di memoria viene copiato direttamente nella superficie di disegno associata. Poiché sullo schermo viene eseguita una sola operazione di disegno, lo sfarfallio dell'immagine associato alle operazioni di disegno complesse viene eliminato.  
  
## <a name="default-double-buffering"></a>Doppio buffer predefinito  
 Il modo più semplice per usare il doppio buffer nelle applicazioni consiste nell'usare il doppio buffer predefinito per form e controlli disponibile in .NET Framework. È possibile abilitare il doppio buffer predefinito per il Windows Forms e i controlli Windows creati impostando la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà su `true` o usando il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo. Per altre informazioni, vedere [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## <a name="manually-managing-buffered-graphics"></a>Gestione manuale delle immagini memorizzate nel buffer  
 Per scenari di doppio buffer più avanzati, ad esempio l'animazione o la gestione avanzata della memoria, è possibile usare le classi di .NET Framework per implementare la propria logica di doppio buffer. La classe responsabile dell'allocazione e della gestione dei singoli buffer grafici è la <xref:System.Drawing.BufferedGraphicsContext> classe. Ogni dominio applicazione dispone <xref:System.Drawing.BufferedGraphicsContext> di un'istanza predefinita che gestisce tutto il doppio buffer predefinito per l'applicazione. Nella maggior parte dei casi sarà presente un solo dominio applicazione per ogni applicazione, pertanto esiste in genere un valore predefinito <xref:System.Drawing.BufferedGraphicsContext> per ogni applicazione. <xref:System.Drawing.BufferedGraphicsContext>Le istanze predefinite vengono gestite dalla <xref:System.Drawing.BufferedGraphicsManager> classe. È possibile recuperare un riferimento all'istanza predefinita chiamando <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager.Current%2A> . È anche possibile creare un' <xref:System.Drawing.BufferedGraphicsContext> istanza dedicata, che può migliorare le prestazioni per le applicazioni a elevato utilizzo di grafica. Per informazioni su come creare un' <xref:System.Drawing.BufferedGraphicsContext> istanza di, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Visualizzazione manuale della grafica memorizzata nel buffer  
 È possibile utilizzare un'istanza della <xref:System.Drawing.BufferedGraphicsContext> classe per creare buffer grafici chiamando <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType> , che restituisce un'istanza della <xref:System.Drawing.BufferedGraphics> classe. Un <xref:System.Drawing.BufferedGraphics> oggetto gestisce un buffer di memoria associato a una superficie di rendering, ad esempio un form o un controllo.  
  
 Dopo la creazione di un'istanza, la <xref:System.Drawing.BufferedGraphics> classe gestisce il rendering in un buffer di grafica in memoria. È possibile eseguire il rendering della grafica nel buffer di memoria tramite <xref:System.Drawing.BufferedGraphics.Graphics%2A> , che espone un <xref:System.Drawing.Graphics> oggetto che rappresenta direttamente il buffer di memoria. È possibile disegnare questo oggetto in modo <xref:System.Drawing.Graphics> analogo a un <xref:System.Drawing.Graphics> oggetto che rappresenta una superficie di disegno. Dopo che tutti i grafici sono stati disegnati nel buffer, è possibile usare <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> per copiare il contenuto del buffer nella superficie di disegno sullo schermo.  
  
 Per ulteriori informazioni sull'utilizzo della <xref:System.Drawing.BufferedGraphics> classe, vedere [rendering manuale di grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md). Per altre informazioni sul rendering della grafica, vedere [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.BufferedGraphics>
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphicsManager>
- [Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md)
- [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)
- [Procedura: Gestire manualmente la grafica memorizzata nel buffer](how-to-manually-manage-buffered-graphics.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
