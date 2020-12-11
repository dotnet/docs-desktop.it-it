---
title: 'Procedura: Appiattire un percorso curvo in una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963385"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Procedura: Appiattire un percorso curvo in una linea
Un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di linee e spline di Bézier. È possibile aggiungere diversi tipi di curve (ellissi, archi, spline cardinali) a un tracciato, ma ogni curva viene convertita in una spline di Bézier prima di essere archiviata nel percorso. L'appiattimento di un tracciato è costituito dalla conversione di ogni spline di Bézier nel percorso a una sequenza di linee rette. Nella figura seguente viene illustrato un percorso prima e dopo l'appiattimento.  
  
 ![Curve e linee rette](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Per rendere flat un tracciato  
  
- chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di planarità che specifica la distanza massima tra il percorso bidimensionale e il percorso originale.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
