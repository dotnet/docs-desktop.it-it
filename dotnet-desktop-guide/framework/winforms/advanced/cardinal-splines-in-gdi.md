---
title: Spline di tipo Cardinal in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 4588f6f606f0f479aeae1d143f23175ec4be32a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952505"
---
# <a name="cardinal-splines-in-gdi"></a>Spline di tipo Cardinal in GDI+
Una spline di tipo Cardinal è una sequenza di curve singole Unite per formare una curva più grande. La spline viene specificata da una matrice di punti e da un parametro di tensione. Una spline Cardinal passa senza problemi a ogni punto della matrice; non ci sono angoli acuti e nessuna modifica brusca della curva. Nella figura seguente viene illustrato un set di punti e una spline di un cardinale che passa attraverso ogni punto del set.  
  
 ![Spline Cardinal](./media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Spline fisiche e matematiche  
 Una spline fisica è un sottile pezzo di legno o altro materiale flessibile. Prima dell'avvento delle spline matematiche, le finestre di progettazione usavano le spline fisiche per creare curve. In una finestra di progettazione la spline viene posizionata su una porzione di carta e ancorata a un set di punti specificato. La finestra di progettazione potrebbe quindi creare una curva disegnando lungo la spline con una penna o una matita. Un determinato set di punti può produrre una serie di curve, a seconda delle proprietà della spline fisica. Una spline con una resistenza elevata al piegamento, ad esempio, produrrebbe una curva diversa rispetto a una spline estremamente flessibile.  
  
 Le formule per le spline matematiche si basano sulle proprietà delle barre flessibili, quindi le curve prodotte dalle spline matematiche sono simili alle curve che sono state generate da spline fisiche. Così come le spline fisiche con tensioni diverse produrranno curve diverse tramite un determinato set di punti, le spline matematiche con valori diversi per il parametro di tensionamento produrranno curve diverse tramite un determinato set di punti. Nella figura seguente sono illustrate quattro spline cardinali che passano attraverso lo stesso set di punti. La tensione viene visualizzata per ogni spline. Una tensione pari a 0 corrisponde alla tensione fisica infinita, forzando la curva ad assumere il modo più breve (linee rette) tra i punti. Una tensione di 1 corrisponde a nessuna tensione fisica, consentendo alla spline di prendere il percorso della curva meno totale. Con i valori di tensionamento maggiori di 1, la curva si comporta come una molla compressa, per cui viene eseguito il push per ottenere un percorso più lungo.  
  
 ![Spline cardinali](./media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 Le quattro spline nell'illustrazione precedente condividono la stessa linea tangente al punto iniziale. La tangente è la linea disegnata dal punto iniziale al punto successivo lungo la curva. Analogamente, la tangente condivisa al punto finale è la linea disegnata dal punto finale al punto precedente della curva.  
  
 Per disegnare una spline di tipo Cardinal, è necessaria un'istanza della <xref:System.Drawing.Graphics> classe, un oggetto <xref:System.Drawing.Pen> e una matrice di <xref:System.Drawing.Point> oggetti. l'istanza della <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo, che disegna la spline, e <xref:System.Drawing.Pen> archivia gli attributi della spline, ad esempio la larghezza e il colore della linea. La matrice di <xref:System.Drawing.Point> oggetti archivia i punti che la curva passerà. Nell'esempio di codice seguente viene illustrato come creare una spline Cardinal che passa attraverso i punti in `myPointArray` . Il terzo parametro è la tensione.  
  
 [!code-csharp[LinesCurvesAndShapes#31](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
