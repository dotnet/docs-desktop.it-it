---
title: "Procedura: impostare l'allineamento orizzontale e verticale di un TileBrush"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
ms.openlocfilehash: e3bfb2b209e40c435c3a321c874dfbd7a9a2fd50
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961309"
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>Procedura: impostare l'allineamento orizzontale e verticale di un TileBrush
Questo esempio spiega come controllare l'allineamento orizzontale e verticale del contenuto in una tessera. Per controllare l'allineamento orizzontale e verticale di un oggetto <xref:System.Windows.Media.TileBrush> , usare le relative <xref:System.Windows.Media.TileBrush.AlignmentX%2A> <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà e.  
  
 Le <xref:System.Windows.Media.TileBrush.AlignmentX%2A> <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà e di un oggetto <xref:System.Windows.Media.TileBrush> vengono utilizzate quando si verifica una delle condizioni seguenti:  
  
- La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà è <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill> e <xref:System.Windows.Media.TileBrush.Viewbox%2A> e hanno proporzioni <xref:System.Windows.Media.TileBrush.Viewport%2A> diverse.  
  
- La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà è <xref:System.Windows.Media.Stretch.None> e e <xref:System.Windows.Media.TileBrush.Viewbox%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A> sono di dimensioni diverse.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene allineato il contenuto di un oggetto <xref:System.Windows.Media.DrawingBrush> , che è un tipo di <xref:System.Windows.Media.TileBrush> , nell'angolo superiore sinistro del relativo riquadro. Per allineare il contenuto, nell'esempio viene impostata la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà di <xref:System.Windows.Media.DrawingBrush> su <xref:System.Windows.Media.AlignmentX.Left> e la <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà su <xref:System.Windows.Media.AlignmentY.Top> . Questo esempio produce il seguente output:  
  
 ![TileBrush con allineamento in alto a sinistra](./media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
TileBrush con contenuto allineato all'angolo superiore sinistro  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio successivo il contenuto di un oggetto viene allineato all' <xref:System.Windows.Media.DrawingBrush> angolo inferiore destro del relativo riquadro impostando la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà su <xref:System.Windows.Media.AlignmentX.Right> e la <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà su <xref:System.Windows.Media.AlignmentY.Bottom> . Questo esempio produce l'output seguente.  
  
 ![TileBrush con allineamento in basso a destra](./media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
TileBrush con contenuto allineato all'angolo in basso a destra  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio successivo il contenuto di un oggetto viene allineato all' <xref:System.Windows.Media.DrawingBrush> angolo superiore sinistro del relativo riquadro impostando la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà su <xref:System.Windows.Media.AlignmentX.Left> e la <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà su <xref:System.Windows.Media.AlignmentY.Top> . Imposta inoltre l'oggetto <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> dell'oggetto <xref:System.Windows.Media.DrawingBrush> per produrre un modello di riquadro. Questo esempio produce l'output seguente.  
  
 ![TileBrush affiancato con allineamento in alto a sinistra](./media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
Modello di tessera con contenuto allineato all'angolo superiore sinistro nella tessera di base  
  
 L'illustrazione evidenzia una tessera di base, in modo da mostrarne il modo in cui è allineato il contenuto. Si noti che l' <xref:System.Windows.Media.TileBrush.AlignmentX%2A> impostazione non ha alcun effetto perché il contenuto di <xref:System.Windows.Media.DrawingBrush> riempie completamente la tessera di base in orizzontale.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio finale il contenuto di un oggetto affiancato viene allineato <xref:System.Windows.Media.DrawingBrush> alla parte inferiore destra della tessera di base impostando la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà su <xref:System.Windows.Media.AlignmentX.Right> e la <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà su <xref:System.Windows.Media.AlignmentY.Bottom> . Questo esempio produce l'output seguente.  
  
 ![TileBrush affiancato con allineamento in basso a destra](./media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
Modello di tessera con contenuto allineato all'angolo inferiore destro nella tessera di base  
  
 Anche in questo caso, l' <xref:System.Windows.Media.TileBrush.AlignmentX%2A> impostazione non ha alcun effetto perché il contenuto della <xref:System.Windows.Media.DrawingBrush> riempie completamente la tessera di base in orizzontale.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 Negli esempi <xref:System.Windows.Media.DrawingBrush> vengono utilizzati oggetti per illustrare l'utilizzo delle <xref:System.Windows.Media.TileBrush.AlignmentX%2A> <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà e. Queste proprietà si comportano in modo identico per tutti i pennelli affiancati: <xref:System.Windows.Media.DrawingBrush> , <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.VisualBrush> . Per altre informazioni sui pennelli tessera, vedere [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.VisualBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
