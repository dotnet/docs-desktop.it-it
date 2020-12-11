---
title: 'Procedura: Riempire una forma con un motivo di tratteggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963394"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Procedura: Riempire una forma con un motivo di tratteggio
Un modello di tratteggio è costituito da due colori: uno per lo sfondo e uno per le linee che formano il modello sullo sfondo. Per riempire una forma chiusa con un motivo di tratteggio, usare un <xref:System.Drawing.Drawing2D.HatchBrush> oggetto. Nell'esempio seguente viene illustrato come riempire un'ellisse con un motivo di tratteggio:  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> costruttore accetta tre argomenti: lo stile di tratteggio, il colore della linea di tratteggio e il colore dello sfondo. L'argomento dello stile di tratteggio può essere qualsiasi valore dell' <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione. Sono presenti più di 50 elementi nell' <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione. alcuni di questi elementi sono illustrati nell'elenco seguente:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 Nell'illustrazione seguente viene mostrata l'ellisse piena.  
  
  ![Screenshot dell'aspetto di un'ellisse riempita con un modello di tratteggio.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
