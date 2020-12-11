---
title: Coordinate
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951953"
---
# <a name="windows-forms-coordinates"></a>Coordinate di Windows Form
Il sistema di coordinate per un Windows Form è basato sulle coordinate del dispositivo e l'unità di misura di base durante il disegno in Windows Forms è l'unità del dispositivo, in genere il pixel. I punti sullo schermo sono descritti dalle coppie di coordinate x e y, con le coordinate x che aumentano verso destra e le coordinate y che aumentano dall'alto verso il basso. La posizione dell'origine, relativa allo schermo, può variare a seconda che si specifichino coordinate dello schermo o del client.  
  
## <a name="screen-coordinates"></a>Coordinate dello schermo  
 Una Windows Forms Application specifica la posizione di una finestra sullo schermo nelle coordinate dello schermo. Per le coordinate dello schermo, l'origine è l'angolo superiore sinistro dello schermo. La posizione completa di una finestra è spesso descritta da una <xref:System.Drawing.Rectangle> struttura contenente le coordinate dello schermo di due punti che definiscono gli angoli superiore sinistro e inferiore destro della finestra.  
  
## <a name="client-coordinates"></a>Coordinate client  
 Una Windows Forms Application specifica la posizione dei punti in un form o in un controllo usando le coordinate client. L'origine per le coordinate client è l'angolo superiore sinistro dell'area client del controllo o del form. Le coordinate client assicurano che un'applicazione possa usare valori di coordinate coerenti durante il disegno in un form o in un controllo, indipendentemente dalla posizione del form o del controllo sullo schermo.  
  
 Le dimensioni dell'area client sono descritte anche da una <xref:System.Drawing.Rectangle> struttura che contiene le coordinate client per l'area. In tutti i casi, la coordinata superiore sinistra del rettangolo viene inclusa nell'area client, mentre la coordinata inferiore destra viene esclusa. Le operazioni di grafica non includono i bordi destro e inferiore di un'area client. Il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo, ad esempio, riempie il bordo destro e inferiore del rettangolo specificato, ma non includerà i bordi.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Mapping da un tipo di coordinata a un altro  
 Occasionalmente, potrebbe essere necessario eseguire il mapping dalle coordinate dello schermo alle coordinate client. A tale scopo, è possibile usare i <xref:System.Windows.Forms.Control.PointToClient%2A> <xref:System.Windows.Forms.Control.PointToScreen%2A> metodi e disponibili nella <xref:System.Windows.Forms.Control> classe. Ad esempio, la <xref:System.Windows.Forms.Control.MousePosition%2A> proprietà di <xref:System.Windows.Forms.Control> viene segnalata in coordinate dello schermo, ma è consigliabile convertirle in coordinate client.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
