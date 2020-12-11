---
title: "Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963202"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento
La modalità di interpolazione di un <xref:System.Drawing.Graphics> oggetto influenza il modo in cui GDI+ ridimensiona (estende e compatta) le immagini. L' <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione definisce diverse modalità di interpolazione, alcune delle quali sono mostrate nell'elenco seguente:  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Per estendere un'immagine, è necessario eseguire il mapping di ogni pixel nell'immagine originale a un gruppo di pixel nell'immagine più grande. Per compattare un'immagine, è necessario eseguire il mapping dei gruppi di pixel nell'immagine originale a singoli pixel nell'immagine più piccola. L'efficacia degli algoritmi che eseguono questi mapping determina la qualità di un'immagine ridimensionata. Gli algoritmi che producono immagini con scalabilità di qualità superiore tendono a richiedere più tempo di elaborazione. Nell'elenco precedente <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> è la modalità di qualità più bassa ed <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> è la modalità di qualità più elevata.  
  
 Per impostare la modalità di interpolazione, assegnare uno dei membri dell' <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione alla <xref:System.Drawing.Graphics.InterpolationMode%2A> proprietà di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnata un'immagine, quindi viene compattata l'immagine con tre diverse modalità di interpolazione.  
  
 La figura seguente illustra l'immagine originale e le tre immagini più piccole.  
  
 ![Screenshot che mostra un'immagine con diverse impostazioni di interpolazione.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
