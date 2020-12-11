---
title: 'Procedura: Ruotare, capovolgere e inclinare immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962539"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Procedura: Ruotare, capovolgere e inclinare immagini
È possibile ruotare, riflettere e inclinare un'immagine specificando punti di destinazione per gli angoli superiore sinistro, superiore destro e inferiore sinistro dell'immagine originale. I tre punti di destinazione determinano una trasformazione affine che esegue il mapping dell'immagine rettangolare originale a un parallelogramma.  
  
## <a name="example"></a>Esempio  
 Si supponga, ad esempio, che l'immagine originale sia un rettangolo con angolo superiore sinistro in corrispondenza di (0, 0), angolo superiore destro in corrispondenza di (100, 0) e angolo inferiore sinistro in (0, 50). Si supponga ora di eseguire il mapping di questi tre punti ai punti di destinazione come indicato di seguito.  
  
|Punto originale|Punto di destinazione|  
|--------------------|-----------------------|  
|Superiore sinistro (0,0)|(200, 20)|  
|In alto a destra (100, 0)|(110, 100)|  
|In basso a sinistra (0, 50)|(250, 30)|  
  
 La figura seguente mostra l'immagine originale e l'immagine mappata al parallelogramma. L'immagine originale è stata inclinata, riflessa, ruotata e convertita. L'asse x lungo il bordo superiore dell'immagine originale viene mappato alla riga che esegue fino a (200, 20) e (110, 100). L'asse y lungo il bordo sinistro dell'immagine originale viene mappato alla riga che esegue fino a (200, 20) e (250, 30).  
  
 ![Immagine originale e immagine mappata al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 Nella figura seguente viene illustrata una trasformazione simile applicata a un'immagine fotografica:  
  
 ![Immagine di un scalatore e immagine mappata al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 Nella figura seguente viene illustrata una trasformazione simile applicata a un metafile:  
  
 ![Illustrazione di forme e testo e di cui è stato eseguito il mapping al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 Nell'esempio seguente vengono generate le immagini mostrate nella prima illustrazione.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Assicurarsi di sostituire `Stripes.bmp` con il percorso di un'immagine valida nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
