---
title: 'Procedura: Convertire i colori delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963232"
---
# <a name="how-to-translate-image-colors"></a>Procedura: Convertire i colori delle immagini
Una traduzione aggiunge un valore a uno o più dei quattro componenti del colore. Nella tabella seguente vengono fornite le voci della matrice di colori che rappresentano le traduzioni.  
  
|Componente da tradurre|Voce matrice|  
|--------------------------------|------------------|  
|Rosso|[4][0]|  
|Green|[4][1]|  
|Blu|[4][2]|  
|Alfa|[4][3]|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars.bmp. Il codice aggiunge quindi 0,75 al componente rosso di ogni pixel nell'immagine. L'immagine originale viene disegnata insieme all'immagine trasformata.  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine trasformata a destra:  
  
 ![Screenshot dell'immagine originale e trasformata.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la traduzione rossa. Si noti che poiché il valore massimo per un componente colore è 1, il componente rosso nella seconda riga non cambia. Analogamente, il valore minimo per un componente colore è 0.  
  
|Originale|Convertito|  
|--------------|----------------|  
|Nero (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rosso (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Verde (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Blu (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire `ColorBars.bmp` con il nome e il percorso di un file di immagine validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)
