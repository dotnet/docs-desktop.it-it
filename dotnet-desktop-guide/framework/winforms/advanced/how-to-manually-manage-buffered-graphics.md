---
title: 'Procedura: Gestire manualmente la grafica memorizzata nel buffer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963346"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Procedura: Gestire manualmente la grafica memorizzata nel buffer
Per scenari di doppio buffer più avanzati, è possibile utilizzare le classi .NET Framework per implementare la logica di doppio buffer. La classe responsabile dell'allocazione e della gestione dei singoli buffer grafici è la <xref:System.Drawing.BufferedGraphicsContext> classe. Ogni applicazione dispone di un proprio valore predefinito <xref:System.Drawing.BufferedGraphicsContext> che gestisce tutto il doppio buffer predefinito per l'applicazione. È possibile recuperare un riferimento a questa istanza chiamando il <xref:System.Drawing.BufferedGraphicsManager.Current%2A> .  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Per ottenere un riferimento al BufferedGraphicsContext predefinito  
  
- Impostare la <xref:System.Drawing.BufferedGraphicsManager.Current%2A> proprietà, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > Non è necessario chiamare il `Dispose` metodo sul <xref:System.Drawing.BufferedGraphicsContext> riferimento ricevuto dalla <xref:System.Drawing.BufferedGraphicsManager> classe. <xref:System.Drawing.BufferedGraphicsManager>Gestisce tutte le allocazioni di memoria e la distribuzione per le <xref:System.Drawing.BufferedGraphicsContext> istanze predefinite.  
  
     Per le applicazioni a elevato utilizzo di grafica, ad esempio l'animazione, è possibile migliorare le prestazioni utilizzando un oggetto dedicato <xref:System.Drawing.BufferedGraphicsContext> anziché l'oggetto <xref:System.Drawing.BufferedGraphicsContext> fornito da <xref:System.Drawing.BufferedGraphicsManager> . In questo modo è possibile creare e gestire i buffer grafici singolarmente, senza incorrere nel sovraccarico delle prestazioni della gestione di tutti gli altri elementi grafici memorizzati nel buffer associati all'applicazione, anche se la memoria usata dall'applicazione sarà maggiore.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Per creare un BufferedGraphicsContext dedicato  
  
- Dichiarare e creare una nuova istanza della <xref:System.Drawing.BufferedGraphicsContext> classe, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.BufferedGraphicsContext>
- [Grafica a doppio buffer](double-buffered-graphics.md)
- [Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md)
