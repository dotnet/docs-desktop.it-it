---
title: 'Procedura: Usare una matrice di colori per trasformare un singolo colore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963247"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Procedura: Usare una matrice di colori per trasformare un singolo colore
GDI+ fornisce le <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> classi e per l'archiviazione e la manipolazione delle immagini. <xref:System.Drawing.Image><xref:System.Drawing.Bitmap>gli oggetti e archiviano il colore di ogni pixel come numero a 32 bit: 8 bit per colore rosso, verde, blu e alfa. Ognuno dei quattro componenti è un numero compreso tra 0 e 255, 0 che rappresenta nessuna intensità e 255 che rappresenta l'intensità completa. Il componente alfa specifica la trasparenza del colore: 0 è completamente trasparente e 255 è completamente opaco.  
  
 Un vettore di colore è una tupla con 4 elementi del form (rosso, verde, blu, alfa). Ad esempio, il vettore di colore (0, 255, 0, 255) rappresenta un colore opaco che non ha rosso o blu, ma ha un verde a intensità piena.  
  
 Un'altra convenzione per la rappresentazione dei colori usa il numero 1 per l'intensità piena. Usando tale convenzione, il colore descritto nel paragrafo precedente verrebbe rappresentato dal vettore (0, 1, 0, 1). GDI+ utilizza la convenzione di 1 come intensità completa durante le trasformazioni dei colori.  
  
 È possibile applicare trasformazioni lineari (rotazione, ridimensionamento e così via) ai vettori colori moltiplicando i vettori di colore per una matrice 4 × 4. Tuttavia, non è possibile utilizzare una matrice 4 × 4 per eseguire una conversione (non lineare). Se si aggiunge una quinta coordinata fittizia, ad esempio il numero 1, a ogni vettore di colore, è possibile utilizzare una matrice di 5 × 5 per applicare qualsiasi combinazione di trasformazioni e traduzioni lineari. Una trasformazione costituita da una trasformazione lineare seguita da una traduzione è detta trasformazione affine.  
  
 Si supponga, ad esempio, di voler iniziare con il colore (0,2, 0,0, 0,4, 1,0) e applicare le trasformazioni seguenti:  
  
1. Raddoppiare il componente rosso  
  
2. Aggiungere 0,2 ai componenti rosso, verde e blu  
  
 La moltiplicazione di matrici seguente eseguirà la coppia di trasformazioni nell'ordine elencato.  
  
 ![Screenshot di una matrice di moltiplicazione della trasformazione.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 Gli elementi di una matrice di colori sono indicizzati (in base zero) per riga e quindi colonna. La voce della quinta riga e della terza colonna della matrice M, ad esempio, è indicata da M [4] [2].  
  
 La matrice di identità 5 × 5 (mostrata nella figura seguente) presenta 1S sulla diagonale e sugli zeri in qualsiasi altra posizione. Se si moltiplica un vettore di colore per la matrice di identità, il vettore di colore non cambia. Un modo pratico per formare la matrice di una trasformazione colore consiste nell'iniziare con la matrice di identità e apportare una piccola modifica che produce la trasformazione desiderata.  
  
 ![Screenshot di una matrice di identità 5x5 per la trasformazione dei colori.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 Per una descrizione più dettagliata delle matrici e delle trasformazioni, vedere [sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene accettata un'immagine che corrisponde a un solo colore (0,2, 0,0, 0,4, 1,0) e viene applicata la trasformazione descritta nei paragrafi precedenti.  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine trasformata a destra.  
  
 ![Quadrato viola a sinistra e un quadrato fucsia a destra.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 Il codice nell'esempio seguente usa i passaggi seguenti per eseguire il ricoloring:  
  
1. Inizializzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto.  
  
2. Creare un <xref:System.Drawing.Imaging.ImageAttributes> oggetto e passare l' <xref:System.Drawing.Imaging.ColorMatrix> oggetto al <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo dell' <xref:System.Drawing.Imaging.ImageAttributes> oggetto.  
  
3. Passare l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Ricolorazione di immagini](recoloring-images.md)
- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
