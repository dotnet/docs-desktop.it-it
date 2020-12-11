---
title: Utilizzo delle trasformazioni per scalare i colori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962371"
---
# <a name="using-transformations-to-scale-colors"></a>Utilizzo delle trasformazioni per scalare i colori
Una trasformazione di ridimensionamento moltiplica uno o più dei quattro componenti colore per numero. Nella tabella seguente vengono fornite le voci della matrice di colori che rappresentano il ridimensionamento.  
  
|Componente da ridimensionare|Voce matrice|  
|----------------------------|------------------|  
|Rosso|[0][0]|  
|Green|[1][1]|  
|Blu|[2][2]|  
|Alfa|[3][3]|  
  
## <a name="scaling-one-color"></a>Ridimensionamento di un colore  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars2.bmp. Quindi il codice ridimensiona il componente blu di ogni pixel nell'immagine per un fattore di 2. L'immagine originale viene disegnata insieme all'immagine trasformata.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine ridimensionata a destra:  
  
 ![Screenshot che confronta i colori originali e scalati.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu. Si noti che il componente blu nella quarta barra dei colori è stato compreso tra 0,8 e 0,6. Ciò è dovuto al fatto che GDI+ mantiene solo la parte frazionaria del risultato. Ad esempio, (2) (0.8) = 1,6 e la parte frazionaria di 1,6 è 0,6. La conservazione solo della parte frazionaria garantisce che il risultato sia sempre nell'intervallo [0, 1].  
  
|Originale|Ridimensionato|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Ridimensionamento di più colori  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars2.bmp. Il codice Ridimensiona quindi i componenti rosso, verde e blu di ogni pixel nell'immagine. I componenti rossi vengono ridimensionati fino al 25%, i componenti verdi vengono ridimensionati fino al 35% e i componenti blu vengono ridimensionati fino al 50%.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine ridimensionata a destra:  
  
 ![Screenshot che confronta i colori originali e scalati.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.  
  
|Originale|Ridimensionato|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)
