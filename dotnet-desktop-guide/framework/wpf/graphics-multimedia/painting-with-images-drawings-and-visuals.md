---
title: Disegnare con oggetti Image, Drawing e Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: 292f9dcdb6d3ccbb6a3c7192ea6ba44a099ec5d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960748"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Disegnare con oggetti Image, Drawing e Visual
In questo argomento viene descritto come <xref:System.Windows.Media.ImageBrush> utilizzare <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> gli oggetti, e per disegnare un'area con un'immagine, un oggetto <xref:System.Windows.Media.Drawing> o un oggetto <xref:System.Windows.Media.Visual> .  

<a name="prereqs"></a>
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di pennelli forniti da [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] e le relative funzionalità di base. Per un'introduzione, vedere [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>Disegnare un'area con un'immagine  
 <xref:System.Windows.Media.ImageBrush>Disegna un'area con un oggetto <xref:System.Windows.Media.ImageSource> . Il tipo più comune di <xref:System.Windows.Media.ImageSource> da utilizzare con un <xref:System.Windows.Media.ImageBrush> è un oggetto <xref:System.Windows.Media.Imaging.BitmapImage> , che descrive un'immagine bitmap. È possibile usare un <xref:System.Windows.Media.DrawingImage> oggetto per disegnare usando un <xref:System.Windows.Media.Drawing> oggetto, ma è più semplice usare invece un oggetto <xref:System.Windows.Media.DrawingBrush> . Per ulteriori informazioni sugli <xref:System.Windows.Media.ImageSource> oggetti, vedere [Cenni preliminari sulla creazione di immagini](imaging-overview.md).  
  
 Per disegnare con un oggetto <xref:System.Windows.Media.ImageBrush> , creare un oggetto <xref:System.Windows.Media.Imaging.BitmapImage> e usarlo per caricare il contenuto della bitmap. Utilizzare quindi <xref:System.Windows.Media.Imaging.BitmapImage> per impostare la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà dell'oggetto <xref:System.Windows.Media.ImageBrush> . Infine, applicare all' <xref:System.Windows.Media.ImageBrush> oggetto che si desidera disegnare.  In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è anche possibile impostare solo la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà dell'oggetto <xref:System.Windows.Media.ImageBrush> con il percorso dell'immagine da caricare.  
  
 Come tutti <xref:System.Windows.Media.Brush> gli oggetti, un oggetto <xref:System.Windows.Media.ImageBrush> può essere usato per disegnare oggetti quali forme, pannelli, controlli e testo. Nella figura seguente vengono illustrati alcuni effetti che è possibile ottenere con un <xref:System.Windows.Media.ImageBrush> .  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Oggetti disegnati con un oggetto ImageBrush  
  
 Per impostazione predefinita, un oggetto <xref:System.Windows.Media.ImageBrush> estende la propria immagine in modo da riempire completamente l'area disegnata, eventualmente distorcendo l'immagine se l'area disegnata presenta proporzioni diverse rispetto all'immagine. È possibile modificare questo comportamento modificando la <xref:System.Windows.Media.TileBrush.Stretch%2A> Proprietà dal valore predefinito di <xref:System.Windows.Media.Stretch.Fill> a <xref:System.Windows.Media.Stretch.None> , <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill> . Poiché <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush> , è possibile specificare esattamente il modo in cui un pennello immagine riempie l'area di output e persino creare modelli. Per ulteriori informazioni sulle <xref:System.Windows.Media.TileBrush> funzionalità avanzate, vedere [Panoramica di TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Esempio: disegnare un oggetto con un'immagine bitmap  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.ImageBrush> per disegnare l'oggetto <xref:System.Windows.Controls.Panel.Background%2A> di un oggetto <xref:System.Windows.Controls.Canvas> .  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>Inserire un disegno in un'area  
 Un oggetto <xref:System.Windows.Media.DrawingBrush> consente di disegnare un'area con forme, testo, immagini e video. Le forme all'interno di un pennello possono essere disegnate con un colore a tinta unita, una sfumatura, un'immagine o anche un'altra <xref:System.Windows.Media.DrawingBrush> . Nella figura seguente vengono illustrati alcuni utilizzi di un oggetto <xref:System.Windows.Media.DrawingBrush> .  
  
 ![Esempi di output di DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Oggetti disegnati con un oggetto DrawingBrush  
  
 <xref:System.Windows.Media.DrawingBrush>Disegna un'area con un <xref:System.Windows.Media.Drawing> oggetto. <xref:System.Windows.Media.Drawing>Oggetto che descrive il contenuto visibile, ad esempio una forma, una bitmap, un video o una riga di testo. Tipi diversi di disegni descrivono tipi diversi di contenuto. L'elenco seguente contiene i vari tipi di oggetti Drawing.  
  
- <xref:System.Windows.Media.GeometryDrawing> : Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing> : Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> : Disegna il testo.  
  
- <xref:System.Windows.Media.VideoDrawing> : Riproduce un file audio o video.  
  
- <xref:System.Windows.Media.DrawingGroup> : Disegna altri disegni. È possibile usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Per ulteriori informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
 Analogamente a un oggetto <xref:System.Windows.Media.ImageBrush> , un oggetto <xref:System.Windows.Media.DrawingBrush> estende <xref:System.Windows.Media.DrawingBrush.Drawing%2A> per riempire l'area di output. È possibile eseguire l'override di questo comportamento modificando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita di <xref:System.Windows.Media.Stretch.Fill> . Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>Esempio: disegnare un oggetto con un oggetto Drawing  
 L'esempio seguente illustra come disegnare un oggetto con un disegno di tre ellissi. Un oggetto <xref:System.Windows.Media.GeometryDrawing> viene utilizzato per descrivere i puntini di sospensione.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>Disegnare un'area con un oggetto Visual  
 Il più versatile e potente di tutti i pennelli, <xref:System.Windows.Media.VisualBrush> Disegna un'area con un oggetto <xref:System.Windows.Media.Visual> . Un <xref:System.Windows.Media.Visual> è un tipo grafico di basso livello che funge da predecessore di molti componenti grafici utili. Ad esempio, le <xref:System.Windows.Window> <xref:System.Windows.FrameworkElement> classi, e <xref:System.Windows.Controls.Control> sono tutti tipi di <xref:System.Windows.Media.Visual> oggetti. Utilizzando un <xref:System.Windows.Media.VisualBrush> è possibile disegnare aree con quasi tutti gli [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] oggetti grafici.  
  
> [!NOTE]
> Sebbene <xref:System.Windows.Media.VisualBrush> sia un tipo di <xref:System.Windows.Freezable> oggetto, non può essere bloccato (reso di sola lettura) quando la relativa <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà è impostata su un valore diverso da `null` .  
  
 Esistono due modi per specificare il <xref:System.Windows.Media.VisualBrush.Visual%2A> contenuto di un oggetto <xref:System.Windows.Media.VisualBrush> .  
  
- Creare un nuovo oggetto <xref:System.Windows.Media.Visual> e usarlo per impostare la <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà dell'oggetto <xref:System.Windows.Media.VisualBrush> . Per un esempio, vedere la sezione [Esempio: disegnare un oggetto con un oggetto Visual](#examplevisualbrush1) seguente.  
  
- Usare un oggetto esistente <xref:System.Windows.Media.Visual> , che crea un'immagine duplicata della destinazione <xref:System.Windows.Media.Visual> . È quindi possibile usare <xref:System.Windows.Media.VisualBrush> per creare effetti interessanti, ad esempio la reflection e l'ingrandimento. Per un esempio, vedere la sezione [Esempio: creare una reflection](#examplevisualbrush2).  
  
 Quando si definisce un nuovo oggetto <xref:System.Windows.Media.VisualBrush.Visual%2A> per un oggetto <xref:System.Windows.Media.VisualBrush> e che <xref:System.Windows.Media.Visual> è un oggetto <xref:System.Windows.UIElement> (ad esempio un pannello o un controllo), il sistema di layout viene eseguito in <xref:System.Windows.UIElement> e nei relativi elementi figlio quando la <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> proprietà è impostata su `true` . Tuttavia, la radice <xref:System.Windows.UIElement> è essenzialmente isolata dal resto del sistema: gli stili e il layout esterno non può permeare questo limite. Pertanto, è necessario specificare in modo esplicito le dimensioni della radice <xref:System.Windows.UIElement> , poiché l'unico elemento padre è <xref:System.Windows.Media.VisualBrush> e pertanto non può ridimensionarsi automaticamente nell'area da disegnare. Per altre informazioni sul layout in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], vedere [Layout](../advanced/layout.md).  
  
 Come <xref:System.Windows.Media.ImageBrush> e  <xref:System.Windows.Media.DrawingBrush> , un oggetto <xref:System.Windows.Media.VisualBrush> estende il contenuto per riempire l'area di output. È possibile eseguire l'override di questo comportamento modificando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà dall'impostazione predefinita di <xref:System.Windows.Media.Stretch.Fill> . Per altre informazioni, vedere la proprietà <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>Esempio: disegnare un oggetto con un oggetto Visual  
 L'esempio seguente usa numerosi controlli e un pannello per disegnare un rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>Esempio: creare una reflection  
 Nell'esempio precedente è stato illustrato come creare un nuovo oggetto <xref:System.Windows.Media.Visual> da utilizzare come sfondo. È anche possibile usare un oggetto <xref:System.Windows.Media.VisualBrush> per visualizzare un oggetto visivo esistente. questa funzionalità consente di produrre effetti visivi interessanti, ad esempio reflection e ingrandimento. Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.VisualBrush> per creare un riflesso di un oggetto <xref:System.Windows.Controls.Border> che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto Visual riflesso](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per altri esempi che illustrano come ingrandire parti dello schermo e come creare reflection, vedere [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>Funzionalità degli oggetti TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush> sono tipi di <xref:System.Windows.Media.TileBrush> oggetti. <xref:System.Windows.Media.TileBrush> gli oggetti forniscono una grande quantità di controllo sulla modalità di disegno di un'area con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Un oggetto è costituito da <xref:System.Windows.Media.TileBrush> tre componenti principali: contenuto, riquadri e area di output.  
  
 ![Componenti di TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di un oggetto TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con più tessere  
  
 Per ulteriori informazioni sulle funzionalità di affiancamento degli <xref:System.Windows.Media.TileBrush> oggetti, vedere [Cenni preliminari](tilebrush-overview.md)sugli oggetti TileBrush.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Cenni preliminari sugli oggetti TileBrush](tilebrush-overview.md)
- [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md)
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sulle maschere di opacità](opacity-masks-overview.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
