---
title: Regioni in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952800"
---
# <a name="regions-in-gdi"></a>Regioni in GDI+
Un'area è una parte dell'area di visualizzazione di un dispositivo di output. Le aree possono essere semplici (un solo rettangolo) o complesse (una combinazione di poligoni e curve chiuse). Nella figura seguente sono illustrate due aree: una costruita da un rettangolo e l'altra costruita da un percorso.  
  
 ![Aree](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Utilizzo delle regioni  
 Le aree vengono spesso usate per il ritaglio e l'hit testing. Il ritaglio implica la limitazione del disegno a una determinata area dell'area di visualizzazione, in genere la parte che deve essere aggiornata. L'hit testing prevede il controllo per determinare se il cursore si trova in una determinata area dello schermo quando viene premuto un pulsante del mouse.  
  
 È possibile costruire un'area da un rettangolo o da un percorso. È anche possibile creare aree complesse combinando le aree esistenti. La <xref:System.Drawing.Region> classe fornisce i metodi seguenti per combinare le aree: <xref:System.Drawing.Region.Intersect%2A> ,, <xref:System.Drawing.Region.Union%2A> <xref:System.Drawing.Region.Xor%2A> , <xref:System.Drawing.Region.Exclude%2A> e <xref:System.Drawing.Region.Complement%2A> .  
  
 L'intersezione di due aree è il set di tutti i punti appartenenti a entrambe le aree. L'Unione è il set di tutti i punti che appartengono a una o all'altra o a entrambe le aree. Il complemento di un'area è il set di tutti i punti che non sono presenti nell'area. Nella figura seguente sono illustrate l'intersezione e l'Unione delle due aree illustrate nella figura precedente.  
  
 ![Aree](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 Il <xref:System.Drawing.Region.Xor%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti che appartengono a un'area o l'altra, ma non entrambi. Il <xref:System.Drawing.Region.Exclude%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti della prima area che non si trovano nella seconda area. Nella figura seguente sono illustrate le aree risultanti dall'applicazione dei <xref:System.Drawing.Region.Xor%2A> <xref:System.Drawing.Region.Exclude%2A> metodi e alle due aree illustrate all'inizio di questo argomento.  
  
 ![Aree](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Per riempire un'area, sono necessari un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Brush> oggetto e un <xref:System.Drawing.Region> oggetto. L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.FillRegion%2A> metodo e l' <xref:System.Drawing.Brush> oggetto archivia gli attributi del riempimento, ad esempio il colore o il modello. Nell'esempio seguente viene riempita un'area con un colore a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Utilizzo delle regioni](using-regions.md)
