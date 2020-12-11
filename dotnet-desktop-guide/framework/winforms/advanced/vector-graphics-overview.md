---
title: Cenni preliminari sulla grafica vettoriale
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 6f405f5ffc67a0cdb13fe83f4dd36b70769a4cd9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962368"
---
# <a name="vector-graphics-overview"></a>Cenni preliminari sulla grafica vettoriale
GDI+ disegna linee, rettangoli e altre forme in un sistema di coordinate. È possibile scegliere da un'ampia gamma di sistemi di coordinate, ma il sistema di coordinate predefinito ha l'origine nell'angolo superiore sinistro con l'asse x che punta verso destra e l'asse y che punta verso il basso. L'unità di misura del sistema di coordinate predefinito è il pixel.  
  
## <a name="the-building-blocks-of-gdi"></a>Blocchi predefiniti di GDI+  
 ![Grafica vettoriale](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Un monitor del computer crea la propria visualizzazione su una matrice rettangolare di punti detti elementi immagine o pixel. Il numero di pixel visualizzati sullo schermo varia da un monitoraggio a quello successivo e il numero di pixel visualizzati in un singolo monitoraggio può in genere essere configurato a un certo livello dall'utente.  
  
 ![Grafica vettoriale](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Quando si utilizza GDI+ per disegnare una linea, un rettangolo o una curva, si forniscono determinate informazioni chiave sull'elemento da disegnare. È ad esempio possibile specificare una riga fornendo due punti ed è possibile specificare un rettangolo fornendo un punto, un'altezza e una larghezza. GDI+ funziona in combinazione con il software del driver di visualizzazione per determinare quali pixel devono essere attivati per mostrare la linea, il rettangolo o la curva. Nella figura seguente vengono mostrati i pixel accesi per visualizzare una riga dal punto (4, 2) al punto (12, 8).  
  
 ![Grafica vettoriale](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Nel tempo, alcuni blocchi predefiniti di base si sono dimostrati più utili per la creazione di immagini bidimensionali. Questi blocchi predefiniti, tutti supportati da GDI+, sono indicati nell'elenco seguente:  
  
- Linee  
  
- Rettangoli  
  
- Ellissi  
  
- Archi  
  
- Poligoni  
  
- Spline cardinali  
  
- spline di Bézier  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Metodi per il disegno con un oggetto Graphics  
 La <xref:System.Drawing.Graphics> classe in GDI+ fornisce i metodi seguenti per disegnare gli elementi nell'elenco precedente: <xref:System.Drawing.Graphics.DrawLine%2A> ,, <xref:System.Drawing.Graphics.DrawRectangle%2A> <xref:System.Drawing.Graphics.DrawEllipse%2A> , <xref:System.Drawing.Graphics.DrawPolygon%2A> , <xref:System.Drawing.Graphics.DrawArc%2A> , <xref:System.Drawing.Graphics.DrawCurve%2A> (per le spline cardinalhe) e <xref:System.Drawing.Graphics.DrawBezier%2A> . Ognuno di questi metodi è sovraccarico; ovvero, ogni metodo supporta diversi elenchi di parametri diversi. Ad esempio, una variante del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro Integer, mentre un'altra variante del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per disegnare linee, rettangoli e spline di Bézier hanno metodi complementari plurali che disegnano più elementi in una singola chiamata: <xref:System.Drawing.Graphics.DrawLines%2A> , <xref:System.Drawing.Graphics.DrawRectangles%2A> e <xref:System.Drawing.Graphics.DrawBeziers%2A> . Inoltre, il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo dispone di un metodo complementare, <xref:System.Drawing.Graphics.DrawClosedCurve%2A> , che chiude una curva connettendo il punto finale della curva al punto iniziale.  
  
 Tutti i metodi di disegno della <xref:System.Drawing.Graphics> classe operano insieme a un <xref:System.Drawing.Pen> oggetto. Per creare qualsiasi elemento, è necessario creare almeno due oggetti, ovvero un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. L' <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio lo spessore della linea e il colore, dell'elemento da disegnare. L' <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti al Metodo Drawing. Ad esempio, una variante del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro Integer, come illustrato nell'esempio seguente, che disegna un rettangolo con una larghezza di 100, un'altezza di 50 e un angolo superiore sinistro di (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
