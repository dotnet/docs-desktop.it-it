---
title: 'Procedura: creare modelli di elementi affiancati differenti con un TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965791"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Procedura: creare modelli di elementi affiancati differenti con un TileBrush
Questo esempio illustra come usare la <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un oggetto <xref:System.Windows.Media.TileBrush> per creare un modello.  
  
 La <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà consente di specificare il modo in cui il contenuto di un oggetto <xref:System.Windows.Media.TileBrush> viene ripetuto, ovvero affiancato per riempire un'area di output. Per creare un modello, impostare <xref:System.Windows.Media.TileBrush.TileMode%2A> su <xref:System.Windows.Media.TileMode.Tile> , <xref:System.Windows.Media.TileMode.FlipX> , <xref:System.Windows.Media.TileMode.FlipY> o <xref:System.Windows.Media.TileMode.FlipXY> . È anche necessario impostare il valore <xref:System.Windows.Media.TileBrush.Viewport%2A> di <xref:System.Windows.Media.TileBrush> in modo che sia più piccolo dell'area da disegnare; in caso contrario, viene prodotto solo un singolo riquadro, indipendentemente dall' <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione usata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati cinque <xref:System.Windows.Media.DrawingBrush> oggetti, ognuno dei quali assegna un' <xref:System.Windows.Media.TileBrush.TileMode%2A> impostazione diversa e li utilizza per disegnare cinque rettangoli. Sebbene in questo esempio venga utilizzata la <xref:System.Windows.Media.DrawingBrush> classe per illustrare il <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamento, la <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà funziona in modo identico per tutti gli <xref:System.Windows.Media.TileBrush> oggetti, ovvero per <xref:System.Windows.Media.ImageBrush> , <xref:System.Windows.Media.VisualBrush> e <xref:System.Windows.Media.DrawingBrush> .  
  
 L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Output dell'esempio di affiancamento di TileBrush](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Modelli di sezioni creati con la proprietà TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Vedere anche

- [Impostare la dimensione degli elementi affiancati di un TileBrush](how-to-set-the-tile-size-for-a-tilebrush.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
