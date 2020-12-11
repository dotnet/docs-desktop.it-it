---
title: 'Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: a6655652a7c5dedb8e183356688972c07a705cbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962587"
---
# <a name="how-to-manually-render-buffered-graphics"></a>Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer
Se si sta gestendo direttamente grafica memorizzata nel buffer, sarà necessario essere in grado di creare ed eseguire il rendering dei buffer grafici. È possibile creare istanze della classe <xref:System.Drawing.BufferedGraphics> associata alle aree di disegno sullo schermo chiamando il metodo <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>. Il metodo crea un'istanza di <xref:System.Drawing.BufferedGraphics> associata a una particolare area di rendering, ad esempio un form o controllo. Una volta creata un'istanza di <xref:System.Drawing.BufferedGraphics>, è possibile disegnare la grafica nel buffer da essa rappresentato tramite la proprietà <xref:System.Drawing.BufferedGraphics.Graphics%2A>. Una volta eseguite tutte le operazioni grafiche, è possibile copiare il contenuto del buffer sullo schermo chiamando il metodo <xref:System.Drawing.BufferedGraphics.Render%2A>.   
  
> [!NOTE]
> Se si esegue direttamente il rendering, l'uso di memoria aumenterà, anche se solo leggermente.  
  
### <a name="to-manually-display-buffered-graphics"></a>Per visualizzare manualmente la grafica memorizzata nel buffer  
  
1. Ottenere un riferimento a un'istanza della classe <xref:System.Drawing.BufferedGraphicsContext>. Per altre informazioni, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md).  
  
2. Creare un'istanza della classe <xref:System.Drawing.BufferedGraphics> chiamando il metodo <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>e, come illustrato nel codice di esempio seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3. Disegnare la grafica nel buffer relativo impostando la proprietà <xref:System.Drawing.BufferedGraphics.Graphics%2A>. Esempio:  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4. Una volta completate tutte le operazioni di disegno nel buffer grafico, chiamare il metodo <xref:System.Drawing.BufferedGraphics.Render%2A> per eseguire il rendering del buffer, nell'area di disegno associata al buffer, oppure in un'area specificata, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5. Una volta terminato il rendering della grafica, chiamare il metodo `Dispose` sull'istanza di <xref:System.Drawing.BufferedGraphics> per liberare risorse di sistema.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [Grafica a doppio buffer](double-buffered-graphics.md)
- [Procedura: Gestire manualmente la grafica memorizzata nel buffer](how-to-manually-manage-buffered-graphics.md)
