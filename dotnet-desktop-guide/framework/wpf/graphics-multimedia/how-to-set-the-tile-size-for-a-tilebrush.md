---
title: 'Procedura: impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961303"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedura: impostare la dimensione degli elementi affiancati di un TileBrush

In questo esempio viene illustrato come impostare le dimensioni del riquadro per un oggetto <xref:System.Windows.Media.TileBrush> . Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce un unico riquadro che riempie completamente l'area da disegnare. È possibile eseguire l'override di questo comportamento impostando le <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà e.

La <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica le dimensioni del riquadro per un oggetto <xref:System.Windows.Media.TileBrush> . Per impostazione predefinita, il valore della <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alla dimensione dell'area da disegnare. Per fare in modo che la <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifichi una dimensione assoluta, impostare la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà su <xref:System.Windows.Media.BrushMappingMode.Absolute> .

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.ImageBrush> , un tipo di <xref:System.Windows.Media.TileBrush> , per disegnare un rettangolo con riquadri. Nell'esempio viene impostato ogni riquadro su 50% del 50% dell'area di output (rettangolo). Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.

La figura seguente mostra l'output prodotto dall'esempio:

![Rettangolo con quattro ciliege che dimostrano l'affiancamento con un pennello immagine.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

Nell'esempio successivo viene creato un oggetto, ne viene <xref:System.Windows.Media.ImageBrush> impostata la proprietà <xref:System.Windows.Media.TileBrush.Viewport%2A> su e la proprietà su e `0,0,25,25` <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute> viene utilizzata per disegnare un altro rettangolo. Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.

La figura seguente mostra l'output prodotto dall'esempio:

![Rettangolo con 48 ciliege che dimostrano un TileBrush affiancato con un viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Gli esempi precedenti fanno parte di un esempio più esaustivo. Per l'esempio completo, vedere [esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).

Sebbene in questo esempio venga utilizzata la <xref:System.Windows.Media.ImageBrush> classe, le <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà e si comportano in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, ovvero per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush> . Per altre informazioni su <xref:System.Windows.Media.ImageBrush> e sugli altri <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Creare modelli di elementi affiancati differenti con un TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
