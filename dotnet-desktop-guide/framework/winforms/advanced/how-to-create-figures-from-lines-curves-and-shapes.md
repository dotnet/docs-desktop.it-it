---
title: 'Procedura: Creare figure da linee, curve e forme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952133"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Procedura: Creare figure da linee, curve e forme
Per creare una figura, costruire un oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> , quindi chiamare i metodi, ad esempio <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> , per aggiungere primitive al percorso.  
  
## <a name="example"></a>Esempio  
 Negli esempi di codice seguenti vengono creati percorsi con figure:  
  
- Nel primo esempio viene creato un percorso con una sola figura. La figura è costituita da un singolo arco. L'arco ha un angolo di sweep di – 180 gradi, che è in senso antiorario nel sistema di coordinate predefinito.  
  
- Nel secondo esempio viene creato un percorso con due figure. La prima figura è un arco seguito da una riga. La seconda figura è una riga seguita da una curva seguita da una riga. La prima figura viene lasciata aperta e la seconda figura viene chiusa.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
