---
title: Cenni preliminari sulle proprietà di trasformazione Brush
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 7616e1620c0bd342e3c8bb776e8d72c038bd3cc6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965686"
---
# <a name="brush-transformation-overview"></a>Cenni preliminari sulle proprietà di trasformazione Brush
La classe Brush fornisce due proprietà di trasformazione: <xref:System.Windows.Media.Brush.Transform%2A> e <xref:System.Windows.Media.Brush.RelativeTransform%2A> . Le proprietà consentono di ruotare, ridimensionare, inclinare e traslare il contenuto di un pennello. Questo argomento descrive le differenze tra le due proprietà e contiene gli esempi di uso.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario capire le funzionalità del pennello che viene trasformato. Per <xref:System.Windows.Media.LinearGradientBrush> e <xref:System.Windows.Media.RadialGradientBrush> , vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md). Per <xref:System.Windows.Media.ImageBrush> , <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> , vedere  [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md). È anche necessario avere familiarità con le trasformazioni 2D descritte in [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Differenze tra le proprietà Transform e RelativeTransform  
 Quando si applica una trasformazione alla proprietà di un pennello <xref:System.Windows.Media.Brush.Transform%2A> , è necessario conoscere le dimensioni dell'area disegnata se si desidera trasformare il contenuto del pennello intorno al relativo centro. Si supponga che l'area disegnata sia pari a 200 Device Independent Pixel di larghezza e 150 di altezza.  Se è stato usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare l'output del pennello 45 gradi sul proprio centro, si darebbe <xref:System.Windows.Media.RotateTransform> a <xref:System.Windows.Media.RotateTransform.CenterX%2A> di 100 e a <xref:System.Windows.Media.RotateTransform.CenterY%2A> 75.  
  
 Quando si applica una trasformazione alla proprietà di un pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A> , tale trasformazione viene applicata al pennello prima che venga eseguito il mapping dell'output all'area disegnata. L'elenco seguente indica l'ordine in base al quale il contenuto di un pennello viene elaborato e trasformato.  
  
1. Elaborare il contenuto del pennello. Per un oggetto <xref:System.Windows.Media.GradientBrush> , ciò significa determinare l'area della sfumatura. Per un oggetto <xref:System.Windows.Media.TileBrush> , <xref:System.Windows.Media.TileBrush.Viewbox%2A> viene eseguito il mapping di a <xref:System.Windows.Media.TileBrush.Viewport%2A> . Questo diventa l'output del pennello.  
  
2. Proiettare l'output del pennello sul rettangolo di trasformazione 1 x 1.  
  
3. Applicare il pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A> , se ne è presente uno.  
  
4. Proiettare l'output trasformato sull'area da disegnare.  
  
5. Applicare il pennello <xref:System.Windows.Media.Transform> , se ne è presente uno.  
  
 Poiché <xref:System.Windows.Media.Brush.RelativeTransform%2A> viene applicato quando viene eseguito il mapping dell'output del pennello a un rettangolo 1 x 1, i valori di centro trasformazione e offset sembrano essere relativi. Se, ad esempio, è stato usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare l'output del pennello 45 gradi sul proprio centro, si darebbe <xref:System.Windows.Media.RotateTransform> a <xref:System.Windows.Media.RotateTransform.CenterX%2A> di 0,5 e a <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0,5.  
  
 La figura seguente mostra l'output di diversi pennelli che sono stati ruotati di 45 gradi usando <xref:System.Windows.Media.Brush.RelativeTransform%2A> le <xref:System.Windows.Media.Brush.Transform%2A> proprietà e.  
  
 ![Proprietà RelativeTransform e Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>Uso di RelativeTransform con TileBrush  
 Poiché i pennelli affiancati sono più complessi di altri pennelli, l'applicazione <xref:System.Windows.Media.Brush.RelativeTransform%2A> di una a una potrebbe produrre risultati imprevisti. Analizzare ad esempio l'immagine seguente.  
  
 ![Immagine di origine](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.ImageBrush> per disegnare un'area rettangolare con l'immagine precedente. Viene applicato un <xref:System.Windows.Media.RotateTransform> oggetto alla <xref:System.Windows.Media.ImageBrush> proprietà dell'oggetto <xref:System.Windows.Media.Brush.RelativeTransform%2A> e la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà viene impostata su <xref:System.Windows.Media.Stretch.UniformToFill> , che deve mantenere le proporzioni dell'immagine quando viene estesa per riempire completamente il rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Nell'esempio viene prodotto l'output seguente:  
  
 ![Output trasformato](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Si noti che l'immagine è distorta, anche se l'oggetto del pennello è <xref:System.Windows.Media.TileBrush.Stretch%2A> stato impostato su <xref:System.Windows.Media.Stretch.UniformToFill> . Questo perché la trasformazione relativa viene applicata dopo che è stato eseguito il mapping del pennello <xref:System.Windows.Media.TileBrush.Viewbox%2A> alla relativa <xref:System.Windows.Media.TileBrush.Viewport%2A> . L'elenco seguente descrive tutti i passaggi del processo.  
  
1. Proietta il contenuto del pennello ( <xref:System.Windows.Media.TileBrush.Viewbox%2A> ) nella relativa tessera di base ( <xref:System.Windows.Media.TileBrush.Viewport%2A> ) utilizzando l'impostazione del pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> .  
  
     ![Allungare l'oggetto Viewbox per adattarlo al viewport](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Proiettare la tessera di base sul rettangolo di trasformazione 1 x 1.  
  
     ![Eseguire il mapping del riquadro di visualizzazione al rettangolo di trasformazione](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Applicare il <xref:System.Windows.Media.RotateTransform> .  
  
     ![Applicare la relativa trasformazione](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Proiettare la tessera di base trasformata sull'area da disegnare.  
  
     ![Proiettare il pennello trasformato nell'area di output](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Esempio - Rotazione di un oggetto ImageBrush di 45 gradi  
 Nell'esempio seguente viene applicato un oggetto <xref:System.Windows.Media.RotateTransform> alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un oggetto <xref:System.Windows.Media.ImageBrush> . Le <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> proprietà e dell'oggetto <xref:System.Windows.Media.RotateTransform.CenterY%2A> sono entrambe impostate su 0,5, ovvero le coordinate relative del punto centrale del contenuto. Di conseguenza, il contenuto del pennello viene ruotato intorno al relativo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Nell'esempio successivo viene anche applicato un oggetto <xref:System.Windows.Media.RotateTransform> a un oggetto <xref:System.Windows.Media.ImageBrush> , ma viene utilizzata la <xref:System.Windows.Media.Brush.Transform%2A> proprietà anziché la <xref:System.Windows.Media.Brush.RelativeTransform%2A> Proprietà. Per ruotare il pennello intorno al relativo centro, <xref:System.Windows.Media.RotateTransform> è necessario che l'oggetto <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> sia impostato su coordinate assolute. Poiché il rettangolo disegnato dal pennello è di 175 per 90 pixel, il punto centrale relativo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Nella figura seguente viene illustrato il pennello senza una trasformazione, con la trasformazione applicata alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con la trasformazione applicata alla <xref:System.Windows.Media.Brush.Transform%2A> Proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli). Per altre informazioni sui pennelli, vedere  [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
