---
title: 'Procedura: Ottenere le misure dei tipi di carattere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963331"
---
# <a name="how-to-obtain-font-metrics"></a>Procedura: Ottenere le misure dei tipi di carattere
La <xref:System.Drawing.FontFamily> classe fornisce i metodi seguenti che recuperano varie metriche per una particolare combinazione famiglia/stile:  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A>FontStyle  
  
 I valori restituiti da questi metodi sono nelle unità di progettazione dei tipi di carattere, quindi sono indipendenti dalle dimensioni e dalle unità di un <xref:System.Drawing.Font> oggetto specifico.  
  
 Nella figura seguente sono illustrate le diverse metriche:
  
 ![Illustrazione delle metriche dei tipi di carattere: ascesa, discesa e interlinea.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono visualizzate le metriche per lo stile regolare della famiglia di caratteri Arial. Il codice crea anche un <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni pari a 16 pixel e visualizza le metriche (in pixel) per quel particolare <xref:System.Drawing.Font> oggetto.  
  
 Nella figura seguente viene illustrato l'output del codice di esempio:
  
 ![Esempio di output di codice per le metriche dei tipi di carattere Arial.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 Prendere nota delle prime due righe di output nell'illustrazione precedente. L' <xref:System.Drawing.Font> oggetto restituisce una dimensione di 16 e l' <xref:System.Drawing.FontFamily> oggetto restituisce un'altezza em di 2.048. Questi due numeri (16 e 2.048) rappresentano la chiave per la conversione tra le unità di progettazione dei tipi di carattere e le unità (in questo caso pixel) dell' <xref:System.Drawing.Font> oggetto.  
  
 Ad esempio, è possibile convertire l'ascesa da unità di progettazione a pixel come indicato di seguito:  
  
 ![Formula che mostra la conversione da unità di progettazione a pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 Il codice seguente posiziona il testo verticalmente impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto. La coordinata y viene aumentata da `font.Height` per ogni nuova riga di testo. La <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> oggetto restituisce l'interlinea (in pixel) per quel particolare <xref:System.Drawing.Font> oggetto. In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19. Si noti che questo è lo stesso numero (arrotondato per eccesso a un numero intero) ottenuto convertendo la metrica di spaziatura riga in pixel.  
  
 Si noti che l'altezza em (detta anche dimensioni o dimensioni em) non è la somma dell'ascesa e della discesa. La somma dell'ascesa e della discesa è detta altezza della cella. L'altezza della cella meno la porta interna è uguale all'altezza em. L'altezza della cella più la porta esterna è uguale all'interlinea.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
