---
title: Cenni preliminari sugli oggetti TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965467"
---
# <a name="tilebrush-overview"></a>Cenni preliminari sugli oggetti TileBrush
<xref:System.Windows.Media.TileBrush> gli oggetti forniscono una grande quantità di controllo sulla modalità di disegno di un'area con un'immagine, <xref:System.Windows.Media.Drawing> o <xref:System.Windows.Media.Visual> . In questo argomento viene descritto come utilizzare le <xref:System.Windows.Media.TileBrush> funzionalità di per ottenere un maggiore controllo sulla modalità di disegno di un'area da parte di un oggetto <xref:System.Windows.Media.ImageBrush> , <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> .  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è utile comprendere come usare le funzionalità di base della <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush> classe, o <xref:System.Windows.Media.VisualBrush> . Per un'introduzione a questi tipi, vedere il [disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>Disegno di un'area mediante tessere  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> , sono <xref:System.Windows.Media.VisualBrush> tipi di <xref:System.Windows.Media.TileBrush> oggetti. I pennelli tessera forniscono un elevato livello di controllo sulla modalità di disegno di un'area con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Il disegno di un'area con un pennello tessera include tre componenti: il contenuto, la tessera di base e l'area di output.  
  
 ![Componenti di TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di un oggetto TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con TileMode impostata su Tile  
  
 L'area di output è l'area da disegnare, ad esempio <xref:System.Windows.Shapes.Shape.Fill%2A> di un oggetto <xref:System.Windows.Shapes.Ellipse> o <xref:System.Windows.Controls.Control.Background%2A> di un oggetto <xref:System.Windows.Controls.Button> . Nelle sezioni successive vengono descritti gli altri due componenti di un oggetto <xref:System.Windows.Media.TileBrush> .  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>Contenuto del pennello  
 Esistono tre tipi diversi di <xref:System.Windows.Media.TileBrush> e ogni oggetto dipinge con un tipo di contenuto diverso.  
  
- Se il pennello è un oggetto <xref:System.Windows.Media.ImageBrush> , questo contenuto è un'immagine che la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà specifica il contenuto di <xref:System.Windows.Media.ImageBrush> .  
  
- Se il pennello è un oggetto <xref:System.Windows.Media.DrawingBrush> , questo contenuto è un disegno. La <xref:System.Windows.Media.DrawingBrush.Drawing%2A> proprietà specifica il contenuto di <xref:System.Windows.Media.DrawingBrush> .  
  
- Se il pennello è un <xref:System.Windows.Media.VisualBrush> , questo contenuto è un oggetto visivo. La <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà specifica il contenuto di <xref:System.Windows.Media.VisualBrush> .  
  
 È possibile specificare la posizione e le dimensioni del <xref:System.Windows.Media.TileBrush> contenuto utilizzando la <xref:System.Windows.Media.TileBrush.Viewbox%2A> proprietà, sebbene sia comune lasciare l'oggetto <xref:System.Windows.Media.TileBrush.Viewbox%2A> impostato sul valore predefinito. Per impostazione predefinita, <xref:System.Windows.Media.TileBrush.Viewbox%2A> è configurato per contenere completamente il contenuto del pennello. Per ulteriori informazioni sulla configurazione di <xref:System.Windows.Controls.Viewbox> , vedere la <xref:System.Windows.Controls.Viewbox> pagina delle proprietà.  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>Tessera di base  
 Un oggetto <xref:System.Windows.Media.TileBrush> proietta il relativo contenuto su una tessera di base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà controlla il modo <xref:System.Windows.Media.TileBrush> in cui il contenuto viene allungato per riempire la tessera di base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà accetta i valori seguenti, definiti dall' <xref:System.Windows.Media.Stretch> enumerazione:  
  
- <xref:System.Windows.Media.Stretch.None>: Il contenuto del pennello non viene allungato per riempire il riquadro.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Il contenuto del pennello viene ridimensionato per adattarsi al riquadro. Poiché l'altezza e la larghezza del contenuto vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali del contenuto. In altre parole, il contenuto del pennello potrebbe essere distorto per adattarsi completamente alla tessera di output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Il contenuto del pennello viene ridimensionato in modo da adattarlo completamente all'interno del riquadro. Vengono mantenute le proporzioni del contenuto.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Il contenuto del pennello viene ridimensionato in modo da riempire completamente l'area di output mantenendo le proporzioni originali del contenuto.  
  
 Nell'immagine seguente vengono illustrate le diverse <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazioni.  
  
 ![TileBrush con impostazioni Stretch diverse](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Nell'esempio seguente viene impostato il contenuto di un oggetto in <xref:System.Windows.Media.ImageBrush> modo che non venga esteso per riempire l'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Per impostazione predefinita, un oggetto <xref:System.Windows.Media.TileBrush> genera un singolo riquadro, ovvero la tessera di base, ed estende il riquadro per riempire completamente l'area di output. È possibile modificare le dimensioni e la posizione della tessera di base impostando <xref:System.Windows.Media.TileBrush.Viewport%2A> le <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà e.  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>Dimensioni della tessera di base  
 La <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà determina le dimensioni e la posizione della tessera di base e la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà determina se l'oggetto <xref:System.Windows.Media.TileBrush.Viewport%2A> è specificato utilizzando coordinate assolute o relative. Se le coordinate sono relative, sono condizionate dalle dimensioni dell'area di output. I punti (0,0) e (1,1) rappresentano rispettivamente l'angolo superiore sinistro e l'angolo inferiore destro dell'area di output. Per specificare che la <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà utilizza coordinate assolute, impostare la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà su <xref:System.Windows.Media.BrushMappingMode.Absolute> .  
  
 Nella figura seguente viene illustrata la differenza nell'output tra un oggetto <xref:System.Windows.Media.TileBrush> con relativo e assoluto <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> . Si noti che ogni immagine illustra un modello affiancato. Nella sezione successiva viene indicato come specificare il modello di affiancamento.  
  
 ![Unità assolute e relative del viewport](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Nell'esempio seguente viene usata un'immagine per creare una tessera di larghezza pari al 50% dell'altezza. La tessera di base viene posizionata nel punto (0,0) dell'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 Nell'esempio seguente vengono impostati i riquadri di un valore <xref:System.Windows.Media.ImageBrush> su 25 per 25 pixel indipendenti dal dispositivo. Poiché <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> sono assoluti, i <xref:System.Windows.Media.ImageBrush> riquadri sono sempre 25 per 25 pixel, indipendentemente dalle dimensioni dell'area da disegnare.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>Comportamento dell'affiancamento  
 Un <xref:System.Windows.Media.TileBrush> produce un modello affiancato quando la tessera di base non riempie completamente l'area di output e viene specificata una modalità di affiancamento diversa <xref:System.Windows.Media.TileMode.None> . Quando il riquadro di un pennello del riquadro non riempie completamente l'area di output, la <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà specifica se la tessera di base deve essere duplicata per riempire l'area di output e, in caso affermativo, la modalità di duplicazione della tessera di base. La <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà accetta i valori seguenti, definiti dall' <xref:System.Windows.Media.TileMode> enumerazione:  
  
- <xref:System.Windows.Media.TileMode.None>: Viene disegnata solo la tessera di base.  
  
- <xref:System.Windows.Media.TileMode.Tile>: Viene disegnata la tessera di base e l'area rimanente viene riempita ripetendo la tessera di base in modo che il bordo destro di una sezione sia adiacente al bordo sinistro della successiva e, analogamente, per la parte inferiore e superiore.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: Uguale a <xref:System.Windows.Media.TileMode.Tile> , ma le colonne alternative dei riquadri vengono capovolte orizzontalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: Uguale a <xref:System.Windows.Media.TileMode.Tile> , ma le righe alternative dei riquadri vengono capovolte verticalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: Combinazione di <xref:System.Windows.Media.TileMode.FlipX> e <xref:System.Windows.Media.TileMode.FlipY> .  
  
 L'immagine seguente illustra le diverse modalità di affiancamento.  
  
 ![TileBrush con impostazioni TileMode diverse](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Nell'esempio seguente viene usata un'immagine per disegnare un rettangolo di larghezza e altezza pari a 100 pixel. Impostando il valore di Brush è <xref:System.Windows.Media.TileBrush.Viewport%2A> stato impostato su 0, 0, 0,25, 0,25, la tessera di base del pennello viene resa 1/4 dell'area di output. Il pennello <xref:System.Windows.Media.TileBrush.TileMode%2A> è impostato su <xref:System.Windows.Media.TileMode.FlipXY> . In questo modo il rettangolo viene riempito con righe di tessere.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Procedure](brushes-how-to-topics.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
