---
title: Importanza dell'ordine delle trasformazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order significance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 08927ebaa460e19e558dce22f39c13c31f0e49d0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962326"
---
# <a name="why-transformation-order-is-significant"></a>Importanza dell'ordine delle trasformazioni
Un singolo <xref:System.Drawing.Drawing2D.Matrix> oggetto può archiviare una singola trasformazione o una sequenza di trasformazioni. Quest'ultimo è denominato trasformazione composita. La matrice di una trasformazione composita viene ottenuta moltiplicando le matrici delle singole trasformazioni.  
  
## <a name="composite-transform-examples"></a>Esempi di trasformazione composita  
 In una trasformazione composita, l'ordine delle singole trasformazioni è importante. Se, ad esempio, si esegue prima la rotazione, quindi si esegue la scalabilità e si traduce, si ottiene un risultato diverso da quello in cui si esegue la prima conversione, quindi si ruota e quindi si ridimensiona. In GDI+, le trasformazioni composite vengono compilate da sinistra a destra. Se S, R e T sono rispettivamente matrici di scala, rotazione e conversione, il prodotto SRT (in questo ordine) è la matrice della trasformazione composita che si ridimensiona prima di tutto, quindi ruota e quindi trasla. La matrice prodotta dal prodotto SRT è diversa dalla matrice prodotta dal prodotto TRS.  
  
 Un ordine è significativo perché le trasformazioni come la rotazione e la scalabilità vengono eseguite rispetto all'origine del sistema di coordinate. Il ridimensionamento di un oggetto centrato nell'origine produce un risultato diverso rispetto alla scalabilità di un oggetto che è stato rimosso dall'origine. Analogamente, la rotazione di un oggetto centrato nell'origine produce un risultato diverso rispetto alla rotazione di un oggetto che è stato rimosso dall'origine.  
  
 Nell'esempio seguente vengono combinate la scala, la rotazione e la conversione (in questo ordine) per formare una trasformazione composita. L'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato al <xref:System.Drawing.Graphics.RotateTransform%2A> metodo indica che la rotazione seguirà il ridimensionamento. Analogamente, l'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato al <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo indica che la conversione seguirà la rotazione. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> e <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> sono membri dell' <xref:System.Drawing.Drawing2D.MatrixOrder> enumerazione.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 Nell'esempio seguente vengono eseguite le stesse chiamate al metodo dell'esempio precedente, ma l'ordine delle chiamate viene invertito. L'ordine delle operazioni risultante viene innanzitutto convertito, quindi ruotato, quindi ridimensionato, che produce un risultato molto diverso dalla prima scala, quindi ruota e quindi trasla.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Un modo per invertire l'ordine delle singole trasformazioni in una trasformazione composita consiste nell'invertire l'ordine di una sequenza di chiamate al metodo. Un secondo modo per controllare l'ordine delle operazioni consiste nel modificare l'argomento dell'ordine della matrice. L'esempio seguente è identico a quello dell'esempio precedente, ad eccezione del fatto che <xref:System.Drawing.Drawing2D.MatrixOrder.Append> è stato modificato in <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> . La moltiplicazione di matrici viene eseguita nell'ordine SRT, dove S, R e T sono rispettivamente le matrici per la scala, la rotazione e la conversione. L'ordine della trasformazione composita è la prima scala, quindi ruota e quindi trasla.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Il risultato dell'esempio immediatamente precedente è identico a quello del primo esempio di questo argomento. Questo è dovuto al fatto che è stato invertito sia l'ordine delle chiamate al metodo che l'ordine della moltiplicazione di matrici.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.Matrix>
- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Utilizzo di trasformazioni nel codice gestito GDI+](using-transformations-in-managed-gdi.md)
