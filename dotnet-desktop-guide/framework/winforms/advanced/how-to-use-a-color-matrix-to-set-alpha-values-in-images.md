---
title: 'Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962467"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini
La <xref:System.Drawing.Bitmap> classe, che eredita dalla <xref:System.Drawing.Image> classe, e la <xref:System.Drawing.Imaging.ImageAttributes> classe forniscono funzionalità per ottenere e impostare i valori dei pixel. È possibile utilizzare la <xref:System.Drawing.Imaging.ImageAttributes> classe per modificare i valori alfa per un'intera immagine oppure è possibile chiamare il <xref:System.Drawing.Bitmap.SetPixel%2A> metodo della <xref:System.Drawing.Bitmap> classe per modificare i singoli valori dei pixel.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Drawing.Imaging.ImageAttributes> classe dispone di molte proprietà che è possibile utilizzare per modificare le immagini durante il rendering. Nell'esempio seguente <xref:System.Drawing.Imaging.ImageAttributes> viene usato un oggetto per impostare tutti i valori alfa sul 80% di ciò che era. Questa operazione viene eseguita inizializzando una matrice di colori e impostando il valore di scalabilità alfa nella matrice su 0,8. L'indirizzo della matrice di colori viene passato al <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo dell' <xref:System.Drawing.Imaging.ImageAttributes> oggetto e l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo dell' <xref:System.Drawing.Graphics> oggetto.  
  
 Durante il rendering, i valori alfa nella bitmap vengono convertiti nel 80% di ciò che erano. In questo modo si ottiene un'immagine che viene fusa con lo sfondo. Come illustrato nella figura seguente, l'immagine bitmap sembra trasparente; è possibile visualizzare la linea nera a tinta unita.  
  
 ![Screenshot della fusione alfa con una matrice.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "Immagine2")  
  
 Quando l'immagine è sulla parte bianca dello sfondo, l'immagine è stata mescolata con il colore bianco. Quando l'immagine incrocia la linea nera, l'immagine viene fusa con il colore nero.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Linee e riempimenti con fusione alfa](alpha-blending-lines-and-fills.md)
