---
title: 'Procedura: Variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962515"
---
# <a name="how-to-shear-colors"></a>Procedura: Variare le componenti cromatiche
Il taglio aumenta o diminuisce un componente colore di un importo proporzionale a un altro componente colore. Si consideri, ad esempio, la trasformazione in cui il componente rosso viene aumentato di una metà del valore del componente blu. In tale trasformazione, il colore (0,2, 0,5, 1) diventerà (0,7, 0,5, 1). Il nuovo componente rosso è 0,2 + (1/2) (1) = 0,7.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars4.bmp. Il codice applica quindi la trasformazione di taglio descritta nel paragrafo precedente a ogni pixel nell'immagine.  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine tranciata a destra:
  
 ![Due quadrati con strip colorati affiancati che illustrano l'immagine originale e l'immagine tranciata.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la trasformazione di taglio.  
  
|Originale|Tranciati|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire `ColorBars.bmp` con il nome e il percorso di un'immagine validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)
