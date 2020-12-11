---
title: Anti-aliasing con linee e curve
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 871c5cb3cd9356f677633acb04fe82021a9787c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952236"
---
# <a name="antialiasing-with-lines-and-curves"></a>Anti-aliasing con linee e curve
Quando si utilizza GDI+ per creare una linea, si specifica il punto iniziale e il punto finale della linea, ma non è necessario fornire informazioni sui singoli pixel della riga. GDI+ funziona insieme al software per i driver di visualizzazione per determinare quali pixel verranno accesi per visualizzare la riga in un particolare dispositivo di visualizzazione.  
  
## <a name="aliasing"></a>Aliasing  
 Prendere in considerazione la linea rossa diritta che va dal punto (4, 2) al punto (16, 10). Si supponga che il sistema di coordinate abbia l'origine nell'angolo superiore sinistro e che l'unità di misura sia il pixel. Si supponga inoltre che l'asse x punti a destra e che l'asse y punti verso il basso. Nella figura seguente viene illustrata una vista ingrandita della linea rossa disegnata su uno sfondo a più colori.  
  
 ![Linea, senza antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 I pixel rossi utilizzati per il rendering della linea sono opachi. Nessun pixel parzialmente trasparente nella riga. Questo tipo di rendering della linea fornisce un aspetto irregolare alla riga e la linea assomiglia a una scalinata. Questa tecnica di rappresentazione di una linea con una scala è detta aliasing; la scala è un alias per la linea teorica.  
  
## <a name="antialiasing"></a>Anti-aliasing  
 Una tecnica più sofisticata per il rendering di una linea prevede l'uso di pixel parzialmente trasparenti insieme ai pixel opachi. I pixel vengono impostati in rosso puro o in una combinazione di colore rosso e sfondo, a seconda della relativa chiusura. Questo tipo di rendering è denominato anti-aliasing e produce una linea che l'occhio umano percepisce come più uniforme. Nella figura seguente viene illustrato il modo in cui alcuni pixel vengono combinati con lo sfondo per produrre una riga con antialiasing.  
  
 ![Antialiasing di una linea](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 L'anti-aliasing, detto anche smussamento, può essere applicato anche alle curve. La figura seguente mostra una visualizzazione ingrandita di un'ellisse smussata.  
  
 ![Antialiasing di curve](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 La figura seguente mostra la stessa ellisse nelle dimensioni effettive, una volta senza anti-aliasing e una volta con l'anti-aliasing.  
  
 ![Esempio di antialiasing](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Per creare linee e curve che usano l'anti-aliasing, creare un'istanza della <xref:System.Drawing.Graphics> classe e impostarne la <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> . Chiamare quindi uno dei metodi di disegno di quella stessa <xref:System.Drawing.Graphics> classe.  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Usare l'antialiasing nel testo](how-to-use-antialiasing-with-text.md)
