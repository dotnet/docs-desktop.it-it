---
title: 'Procedura: Ruotare i colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963310"
---
# <a name="how-to-rotate-colors"></a>Procedura: Ruotare i colori
La rotazione in uno spazio di colore a quattro dimensioni è difficile da visualizzare. È possibile semplificare la visualizzazione della rotazione accettando che uno dei componenti del colore sia fisso. Si supponga di accettare di tenere il componente alfa fisso a 1 (completamente opaco). Sarà quindi possibile visualizzare uno spazio colore tridimensionale con assi rossi, verdi e blu, come illustrato nella figura seguente.  
  
 ![Illustrazione che mostra la rotazione con assi rossi, verdi e blu.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Un colore può essere considerato come un punto nello spazio 3D. Ad esempio, il punto (1, 0, 0) nello spazio rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.  
  
 Nella figura seguente viene illustrato il significato della rotazione del colore (1, 0, 0) tramite un angolo di 60 gradi nel piano Red-Green. La rotazione in un piano parallelo al piano di Red-Green può essere considerata come rotazione sull'asse blu.  
  
 ![Illustrazione che mostra la rotazione sull'asse blu.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire rotazioni su ognuno dei tre assi delle coordinate (rosso, verde, blu):  
  
 ![Inizializzare una matrice di colori per eseguire rotazioni su tre assi.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene accettata un'immagine che corrisponde a un solo colore (1, 0, 0,6) e viene applicata una rotazione di 60 gradi sull'asse blu. L'angolo della rotazione viene eliminato in un piano parallelo al piano rosso-verde.  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine ruotata a colori a destra:  
  
 ![Illustrazione che mostra le immagini originali e le immagini ruotate a colori.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 Nella figura seguente viene illustrata una visualizzazione della rotazione dei colori eseguita nel codice seguente:
  
 ![Illustrazione che mostra la visualizzazione della rotazione dei colori.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire `RotationInput.bmp` con il nome e il percorso del file di immagine validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)
