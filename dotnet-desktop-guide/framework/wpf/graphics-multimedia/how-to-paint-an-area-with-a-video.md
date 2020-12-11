---
title: "Procedura: disegnare un'area con un video"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968743"
---
# <a name="how-to-paint-an-area-with-a-video"></a>Procedura: disegnare un'area con un video
Questo esempio illustra come disegnare un'area con supporti. Un modo per disegnare un'area con supporti consiste nell'usare un <xref:System.Windows.Controls.MediaElement> insieme a un <xref:System.Windows.Media.VisualBrush> . Utilizzare <xref:System.Windows.Controls.MediaElement> per caricare e riprodurre i supporti, quindi utilizzarlo per impostare la <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà dell'oggetto <xref:System.Windows.Media.VisualBrush> . È quindi possibile usare <xref:System.Windows.Media.VisualBrush> per disegnare un'area con il supporto caricato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Controls.MediaElement> e un oggetto <xref:System.Windows.Media.VisualBrush> per disegnare l'oggetto <xref:System.Windows.Controls.TextBlock.Foreground%2A> di un <xref:System.Windows.Controls.TextBlock> controllo con video. In questo esempio la <xref:System.Windows.Controls.MediaElement.IsMuted%2A> proprietà di viene impostata <xref:System.Windows.Controls.MediaElement> su in `true` modo che non produca alcun suono.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Esempio  
 Poiché <xref:System.Windows.Media.VisualBrush> eredita dalla <xref:System.Windows.Media.TileBrush> classe, fornisce diverse modalità di affiancamento. Impostando la <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.VisualBrush> su e impostando la <xref:System.Windows.Media.TileMode.Tile> relativa <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà su un valore più piccolo dell'area da disegnare, è possibile creare un modello affiancato.  
  
 L'esempio seguente è identico all'esempio precedente, ad eccezione del fatto che <xref:System.Windows.Media.VisualBrush> genera un modello dal video.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Per informazioni sull'aggiunta di un file di contenuto, ad esempio un file multimediale, all'applicazione, vedere la pagina relativa ai [file di dati, di contenuto e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md). Quando si aggiunge un file multimediale, è necessario aggiungerlo come file di contenuto, non come file di risorse.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VisualBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti TileBrush](tilebrush-overview.md)
- [Panoramica delle funzionalità multimediali](multimedia-overview.md)
