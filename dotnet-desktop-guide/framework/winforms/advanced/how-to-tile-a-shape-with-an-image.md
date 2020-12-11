---
title: 'Procedura: Riempire una forma con immagini affiancate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962482"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Procedura: Riempire una forma con immagini affiancate
Così come i riquadri possono essere posizionati uno accanto all'altro per coprire un pavimento, le immagini rettangolari possono essere posizionate l'una accanto all'altra per riempire (affiancare) una forma. Per affiancare l'interno di una forma, utilizzare un pennello di trama. Quando si costruisce un <xref:System.Drawing.TextureBrush> oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto. Quando si usa il pennello trama per disegnare l'interno di una forma, la forma viene riempita con copie ripetute dell'immagine.  
  
 La proprietà modalità a capo dell' <xref:System.Drawing.TextureBrush> oggetto determina il modo in cui l'immagine è orientata mentre viene ripetuta in una griglia rettangolare. È possibile fare in modo che tutti i riquadri nella griglia abbiano lo stesso orientamento oppure è possibile far passare l'immagine da una posizione della griglia a quella successiva. Il capovolgimento può essere orizzontale, verticale o entrambi. Gli esempi seguenti illustrano l'affiancamento con tipi diversi di capovolgimento.  
  
### <a name="to-tile-an-image"></a>Per affiancare un'immagine  
  
- Questo esempio usa l'immagine 75 × 75 seguente per affiancare un rettangolo 200 × 200.  
  
 ![Immagine del riquadro che mostra una casa rossa e una struttura ad albero.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato all'immagine. Si noti che tutti i riquadri hanno lo stesso orientamento; Nessun capovolgimento.  
  
 ![Rettangolo affiancato all'immagine utilizzando lo stesso orientamento per tutti i riquadri.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Per capovolgere un'immagine orizzontalmente durante l'affiancamento  
  
- In questo esempio viene usata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200. La modalità a capo automatico è impostata per capovolgere orizzontalmente l'immagine. Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato all'immagine. Si noti che quando si passa da un riquadro all'altro in una determinata riga, l'immagine viene capovolta orizzontalmente.  
  
 ![Rettangolo affiancato all'immagine capovolto orizzontalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Per capovolgere un'immagine verticalmente durante l'affiancamento  
  
- In questo esempio viene usata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200. La modalità Wrap è impostata per capovolgere l'immagine verticalmente.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Per capovolgere un'immagine orizzontalmente e verticalmente durante l'affiancamento  
  
- In questo esempio viene usata la stessa immagine 75 × 75 per affiancare un rettangolo 200 × 200. La modalità a capo è impostata per capovolgere l'immagine sia orizzontalmente che verticalmente. Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato dall'immagine. Si noti che quando si passa da un riquadro all'altro in una determinata riga, l'immagine viene capovolta orizzontalmente e quando si passa da un riquadro all'altro in una colonna specificata, l'immagine viene capovolta verticalmente.  
  
 ![Rettangolo affiancato all'immagine capovolto orizzontalmente e verticalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
