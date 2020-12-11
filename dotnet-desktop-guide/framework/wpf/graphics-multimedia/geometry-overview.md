---
title: Cenni preliminari sulle classi Geometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: 289a4175652de78d414d7c1d7f4b0697fe4bf243
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966784"
---
# <a name="geometry-overview"></a>Cenni preliminari sulle classi Geometry
In questa panoramica viene descritto come utilizzare le [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> classi per descrivere le forme. Questo argomento contrasta anche le differenze tra <xref:System.Windows.Media.Geometry> oggetti ed <xref:System.Windows.Shapes.Shape> elementi.  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>Definizione di Geometry  
 La <xref:System.Windows.Media.Geometry> classe e le classi che derivano da esso, ad esempio <xref:System.Windows.Media.EllipseGeometry> , <xref:System.Windows.Media.PathGeometry> e <xref:System.Windows.Media.CombinedGeometry> , consentono di descrivere la geometria di una forma 2D. Queste descrizioni geometriche hanno molti usi, come la definizione di una forma da disegnare sullo schermo o la definizione di aree di hit test e di ritaglio. È anche possibile usare un oggetto Geometry per definire un tracciato di animazione.  
  
 <xref:System.Windows.Media.Geometry> gli oggetti possono essere semplici, ad esempio rettangoli e cerchi, o composti, creati da due o più oggetti Geometry.  È possibile creare geometrie più complesse usando le <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> classi e, che consentono di descrivere archi e curve.  
  
 Poiché un <xref:System.Windows.Media.Geometry> è un tipo di <xref:System.Windows.Freezable> , <xref:System.Windows.Media.Geometry> gli oggetti forniscono diverse funzionalità speciali: possono essere dichiarati come [risorse](/dotnet/desktop-wpf/fundamentals/xaml-resources-define), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>Geometrie e forme  
 Le <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Shape> classi e sembrano simili in quanto descrivono entrambe le forme 2D (confrontare <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse> ad esempio), ma esistono differenze importanti.  
  
 Per uno, la <xref:System.Windows.Media.Geometry> classe eredita dalla <xref:System.Windows.Freezable> classe mentre la <xref:System.Windows.Shapes.Shape> classe eredita da <xref:System.Windows.FrameworkElement> . Poiché si tratta di elementi, <xref:System.Windows.Shapes.Shape> gli oggetti possono eseguire il rendering e partecipare al sistema di layout, mentre <xref:System.Windows.Media.Geometry> gli oggetti non possono.  
  
 Sebbene <xref:System.Windows.Shapes.Shape> gli oggetti siano più facilmente utilizzabili degli oggetti <xref:System.Windows.Media.Geometry> , <xref:System.Windows.Media.Geometry> gli oggetti sono più versatili. Mentre un <xref:System.Windows.Shapes.Shape> oggetto viene usato per eseguire il rendering di grafica 2D, un <xref:System.Windows.Media.Geometry> oggetto può essere usato per definire l'area geometrica per la grafica 2D, definire un'area per il ritaglio o definire un'area per l'hit testing, ad esempio.  
  
### <a name="the-path-shape"></a>Classe Path di Shape  
 Uno <xref:System.Windows.Shapes.Shape> , la <xref:System.Windows.Shapes.Path> classe, USA effettivamente un oggetto <xref:System.Windows.Media.Geometry> per descrivere il contenuto. Impostando la <xref:System.Windows.Shapes.Path.Data%2A> proprietà dell'oggetto <xref:System.Windows.Shapes.Path> con un oggetto <xref:System.Windows.Media.Geometry> e impostando le relative <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà e, è possibile eseguire il rendering di un oggetto <xref:System.Windows.Media.Geometry> .  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>Proprietà comuni che richiedono un oggetto Geometry  
 Come indicato nelle sezioni precedenti, gli oggetti Geometry possono essere usati con altri oggetti per vari scopi, ad esempio il disegno di forme, l'animazione e il ritaglio. Nella tabella seguente sono elencate diverse classi con proprietà che accettano un <xref:System.Windows.Media.Geometry> oggetto.  
  
|Tipo|Proprietà|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>Tipi di oggetti Geometry semplici  
 La classe base per tutte le geometrie è la classe astratta <xref:System.Windows.Media.Geometry> .  Le classi che derivano dalla <xref:System.Windows.Media.Geometry> classe possono essere raggruppate approssimativamente in tre categorie: geometrie semplici, geometrie di percorso e geometrie composite.  
  
 Le classi Geometry semplici includono <xref:System.Windows.Media.LineGeometry> , <xref:System.Windows.Media.RectangleGeometry> e <xref:System.Windows.Media.EllipseGeometry> e vengono usate per creare forme geometriche di base, ad esempio linee, rettangoli e cerchi.  
  
- Un <xref:System.Windows.Media.LineGeometry> viene definito specificando il punto iniziale della riga e il punto finale.  
  
- Un <xref:System.Windows.Media.RectangleGeometry> viene definito con una <xref:System.Windows.Rect> struttura che specifica la posizione relativa e l'altezza e la larghezza. È possibile creare un rettangolo arrotondato impostando <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> le <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà e.  
  
- Un oggetto <xref:System.Windows.Media.EllipseGeometry> è definito da un punto centrale, un raggio x e un raggio y.  Gli esempi seguenti mostrano come creare geometrie semplici per il rendering e per il ritaglio.  
  
 Queste stesse forme, oltre a forme più complesse, possono essere create usando <xref:System.Windows.Media.PathGeometry> o combinando oggetti Geometry, ma queste classi forniscono un mezzo più semplice per la produzione di queste forme geometriche di base.  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.LineGeometry> .  Come indicato in precedenza, un <xref:System.Windows.Media.Geometry> oggetto non è in grado di disegnare se stesso, quindi nell'esempio viene utilizzata una <xref:System.Windows.Shapes.Path> forma per eseguire il rendering della riga.  Poiché una linea non dispone di un'area, l'impostazione della <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di <xref:System.Windows.Shapes.Path> non avrà alcun effetto. vengono invece <xref:System.Windows.Shapes.Shape.Stroke%2A> specificate solo le <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà e. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.EllipseGeometry> .  Negli esempi viene impostato il valore <xref:System.Windows.Media.EllipseGeometry.Center%2A> di <xref:System.Windows.Media.EllipseGeometry> è impostato sul punto `50,50` e il raggio x e il raggio y sono entrambi impostati su `50` , che crea un cerchio con un diametro di 100.  L'interno dell'ellisse viene disegnato assegnando un valore alla proprietà Fill dell'elemento Path, in questo caso <xref:System.Windows.Media.Brushes.Gold%2A> . L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Un oggetto EllipseGeometry tracciato a (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.RectangleGeometry> .  La posizione e le dimensioni del rettangolo sono definite da una <xref:System.Windows.Rect> struttura. La posizione è `50,50` e l'altezza e la larghezza sono entrambe `25`; viene creato un quadrato. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Oggetto RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Un oggetto RectangleGeometry tracciato a 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Media.EllipseGeometry> come area di ritaglio per un'immagine.  Un <xref:System.Windows.Controls.Image> oggetto viene definito con un valore <xref:System.Windows.FrameworkElement.Width%2A> di 200 e un <xref:System.Windows.FrameworkElement.Height%2A> di 150.  Un oggetto <xref:System.Windows.Media.EllipseGeometry> con un <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> valore di 100, un <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> valore di 75 e un <xref:System.Windows.Media.EllipseGeometry.Center%2A> valore pari a 100, 75 viene impostato sulla <xref:System.Windows.UIElement.Clip%2A> proprietà dell'immagine.  Verrà visualizzata solo la parte dell'immagine che è all'interno dell'area dell'ellisse. L'immagine seguente illustra l'output dell'esempio.  
  
 ![Immagine con e senza area di ritaglio](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Oggetto EllipseGeometry usato per ritagliare un controllo Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>Geometrie di tracciato  
 La <xref:System.Windows.Media.PathGeometry> classe e il relativo equivalente leggero, <xref:System.Windows.Media.StreamGeometry> ovvero la classe, forniscono i mezzi per descrivere più figure complesse costituite da archi, curve e linee.  
  
 Alla base di un <xref:System.Windows.Media.PathGeometry> è una raccolta di <xref:System.Windows.Media.PathFigure> oggetti, quindi denominata perché ogni figura descrive una forma discreta in <xref:System.Windows.Media.PathGeometry> . Ognuno <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali descrive un segmento della figura.  
  
 Esistono diversi tipi di segmenti.  
  
|Tipo di segmento|Descrizione|Esempio|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco ellittico tra due punti.|[Creare un arco ellittico](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva di Bézier cubica tra due punti.|[Creare una curva di Bezier cubica](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una linea tra due punti.|[Creare un oggetto LineSegment in un oggetto PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie di curve di Bézier cubiche.|Vedere la <xref:System.Windows.Media.PolyBezierSegment> pagina tipo.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie di linee.|Vedere la <xref:System.Windows.Media.PolyLineSegment> pagina tipo.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie di curve di Bézier quadratiche.|Vedere la <xref:System.Windows.Media.PolyQuadraticBezierSegment> pagina.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva di Bézier quadratica.|[Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md).|  
  
 I segmenti all'interno di <xref:System.Windows.Media.PathFigure> vengono combinati in una singola forma geometrica con il punto finale di ogni segmento che è il punto iniziale del segmento successivo. La <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà di un oggetto <xref:System.Windows.Media.PathFigure> specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. È ad esempio possibile definire una linea verticale da a impostando `10,50` `10,150` la <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà su `10,50` e creando un oggetto <xref:System.Windows.Media.LineSegment> con un' <xref:System.Windows.Media.LineSegment.Point%2A> impostazione della proprietà `10,150` .  
  
 Nell'esempio seguente viene creato un oggetto semplice <xref:System.Windows.Media.PathGeometry> costituito da un singolo oggetto <xref:System.Windows.Media.PathFigure> con <xref:System.Windows.Media.LineSegment> e viene visualizzato utilizzando un <xref:System.Windows.Shapes.Path> elemento. L' <xref:System.Windows.Media.PathFigure> oggetto <xref:System.Windows.Media.PathFigure.StartPoint%2A> è impostato su `10,20` e un <xref:System.Windows.Media.LineSegment> è definito con un endpoint di `100,130` . Nella figura seguente viene illustrato l'oggetto <xref:System.Windows.Media.PathGeometry> creato da questo esempio.  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto PathGeometry che contiene un singolo oggetto LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Vale la pena contrastare questo esempio con l' <xref:System.Windows.Media.LineGeometry> esempio precedente.  La sintassi utilizzata per un oggetto <xref:System.Windows.Media.PathGeometry> è molto più dettagliata rispetto a quella usata per un semplice <xref:System.Windows.Media.LineGeometry> e può essere utile usare la <xref:System.Windows.Media.LineGeometry> classe in questo caso, ma la sintassi dettagliata del <xref:System.Windows.Media.PathGeometry> consente aree geometriche estremamente complesse e complesse.  
  
 È possibile creare geometrie più complesse utilizzando una combinazione di <xref:System.Windows.Media.PathSegment> oggetti.  
  
 Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Media.BezierSegment> , un oggetto <xref:System.Windows.Media.LineSegment> e un oggetto <xref:System.Windows.Media.ArcSegment> per creare la forma. Nell'esempio viene innanzitutto creata una curva di Bezier cubica definendo quattro punti, ovvero un punto iniziale, ovvero il punto finale del segmento precedente, un punto finale ( <xref:System.Windows.Media.BezierSegment.Point3%2A> ) e due punti di controllo ( <xref:System.Windows.Media.BezierSegment.Point1%2A> e <xref:System.Windows.Media.BezierSegment.Point2%2A> ).  I due punti di controllo di una curva di Beziér cubica si comportano come magneti, ovvero attraggono parti della linea che sarebbe altrimenti una linea retta, producendo una curva. Il primo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point1%2A> , influiscono sulla parte iniziale della curva; il secondo punto di controllo, <xref:System.Windows.Media.BezierSegment.Point2%2A> , influiscono sulla parte finale della curva.  
  
 Nell'esempio viene quindi aggiunto un oggetto <xref:System.Windows.Media.LineSegment> , che viene tracciato tra il punto finale del precedente <xref:System.Windows.Media.BezierSegment> che lo precedeva al punto specificato dalla relativa <xref:System.Windows.Media.LineSegment> Proprietà.  
  
 Nell'esempio viene quindi aggiunto un oggetto <xref:System.Windows.Media.ArcSegment> , che viene disegnato dal punto finale del precedente <xref:System.Windows.Media.LineSegment> al punto specificato dalla relativa <xref:System.Windows.Media.ArcSegment.Point%2A> Proprietà. Nell'esempio vengono inoltre specificati i valori x e y dell'arco ( <xref:System.Windows.Media.ArcSegment.Size%2A> ), un angolo di rotazione ( <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> ), un flag che indica la dimensione dell'angolo dell'arco risultante ( <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> ) e un valore che indica la direzione in cui viene disegnato l'arco ( <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> ). La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 È possibile creare geometrie ancora più complesse usando più <xref:System.Windows.Media.PathFigure> oggetti all'interno di un oggetto <xref:System.Windows.Media.PathGeometry> .  
  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Media.PathGeometry> con due <xref:System.Windows.Media.PathFigure> oggetti, ognuno dei quali contiene più <xref:System.Windows.Media.PathSegment> oggetti.  Viene usato l'oggetto dell' <xref:System.Windows.Media.PathFigure> esempio precedente e un oggetto <xref:System.Windows.Media.PathFigure> con un oggetto <xref:System.Windows.Media.PolyLineSegment> e un oggetto <xref:System.Windows.Media.QuadraticBezierSegment> .  Un <xref:System.Windows.Media.PolyLineSegment> viene definito con una matrice di punti e <xref:System.Windows.Media.QuadraticBezierSegment> viene definito con un punto di controllo e un punto finale. La figura seguente mostra la forma creata da questo esempio.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Un oggetto PathGeometry con più figure  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Analogamente alla <xref:System.Windows.Media.PathGeometry> classe, un oggetto <xref:System.Windows.Media.StreamGeometry> definisce una forma geometrica complessa che può contenere curve, archi e linee. Diversamente da <xref:System.Windows.Media.PathGeometry> , il contenuto di un oggetto non  <xref:System.Windows.Media.StreamGeometry> supporta data binding, l'animazione o la modifica. Utilizzare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera il sovraccarico del supporto di data binding, animazioni o modifiche. Grazie alla relativa efficienza, la <xref:System.Windows.Media.StreamGeometry> classe è la scelta ideale per la descrizione degli Adorner.  
  
 Per un esempio, vedere [Creare forme tramite un oggetto StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Sintassi di markup del percorso  
 I <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> tipi e supportano la [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] sintassi di un attributo usando una serie speciale di comandi di spostamento e di progetto. Per altre informazioni, vedere [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>Oggetti Geometry composti  
 È possibile creare oggetti Geometry compositi usando un oggetto <xref:System.Windows.Media.GeometryGroup> , un oggetto <xref:System.Windows.Media.CombinedGeometry> o chiamando il <xref:System.Windows.Media.Geometry> metodo statico <xref:System.Windows.Media.Geometry.Combine%2A> .  
  
- L' <xref:System.Windows.Media.CombinedGeometry> oggetto e il <xref:System.Windows.Media.Geometry.Combine%2A> metodo eseguono un'operazione booleana per combinare l'area definita da due geometrie. <xref:System.Windows.Media.Geometry> gli oggetti senza area vengono eliminati. <xref:System.Windows.Media.Geometry>È possibile combinare solo due oggetti, anche se queste due geometrie possono essere anche geometrie composite.  
  
- La <xref:System.Windows.Media.GeometryGroup> classe crea una combinazione degli <xref:System.Windows.Media.Geometry> oggetti che contiene senza combinare la relativa area. <xref:System.Windows.Media.Geometry>È possibile aggiungere qualsiasi numero di oggetti a un oggetto <xref:System.Windows.Media.GeometryGroup> . Per un esempio, vedere [Creare una forma composta](how-to-create-a-composite-shape.md).  
  
 Poiché non eseguono un'operazione di combinazione, l'utilizzo di <xref:System.Windows.Media.GeometryGroup> oggetti fornisce vantaggi in merito alle prestazioni rispetto all'utilizzo di <xref:System.Windows.Media.CombinedGeometry> oggetti o al <xref:System.Windows.Media.Geometry.Combine%2A> metodo.  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>Geometrie combinate  
 La sezione precedente ha indicato l' <xref:System.Windows.Media.CombinedGeometry> oggetto e il <xref:System.Windows.Media.Geometry.Combine%2A> Metodo combinano l'area definita dalle geometrie che contengono. L' <xref:System.Windows.Media.GeometryCombineMode> enumerazione specifica il modo in cui vengono combinate le geometrie. I valori possibili per la <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà sono: <xref:System.Windows.Media.GeometryCombineMode.Union> , <xref:System.Windows.Media.GeometryCombineMode.Intersect> , <xref:System.Windows.Media.GeometryCombineMode.Exclude> e <xref:System.Windows.Media.GeometryCombineMode.Xor> .  
  
 Nell'esempio seguente <xref:System.Windows.Media.CombinedGeometry> viene definito un oggetto con una modalità di combinazione di Union.  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di <xref:System.Windows.Media.GeometryCombineMode.Xor> .  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Per altri esempi, vedere [Creare una forma composta](how-to-create-a-composite-shape.md) e [Creare una geometria combinata](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla <xref:System.Windows.Freezable> classe, la <xref:System.Windows.Media.Geometry> classe fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Geometry> gli oggetti possono essere dichiarati come [risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define), condivisi tra più oggetti, resi di sola lettura per migliorare le prestazioni, clonati e resi thread-safe. Per ulteriori informazioni sulle diverse funzionalità fornite dagli <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>Altre funzionalità dell'oggetto Geometry  
 La <xref:System.Windows.Media.Geometry> classe fornisce anche metodi di utilità utili, come i seguenti:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A> : Ottiene l'area dell'oggetto <xref:System.Windows.Media.Geometry> .  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A> : Determina se la geometria contiene un altro oggetto <xref:System.Windows.Media.Geometry> .  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A> : Determina se il tratto di un oggetto <xref:System.Windows.Media.Geometry> contiene un punto specificato.  
  
 <xref:System.Windows.Media.Geometry>Per un elenco completo dei relativi metodi, vedere la classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintassi di markup del percorso](path-markup-syntax.md)
- [Procedure](geometries-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
