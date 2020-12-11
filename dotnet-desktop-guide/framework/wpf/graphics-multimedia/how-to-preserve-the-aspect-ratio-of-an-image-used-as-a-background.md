---
title: "Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo"
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960799"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di un oggetto per <xref:System.Windows.Media.ImageBrush> mantenere le proporzioni dell'immagine.  
  
 Per impostazione predefinita, quando si usa un oggetto <xref:System.Windows.Media.ImageBrush> per disegnare un'area, il contenuto viene esteso in modo da riempire completamente l'area di output. Quando l'area di output e l'immagine hanno proporzioni diverse, l'immagine risulta distorta dall'adattamento.  
  
 Per <xref:System.Windows.Media.ImageBrush> mantenere le proporzioni della relativa immagine, impostare la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà su <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati due <xref:System.Windows.Media.ImageBrush> oggetti per disegnare due rettangoli. Ogni rettangolo è di 300 x 150 pixel e contiene un'immagine di 300 x 300 pixel. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà del primo pennello è impostata su <xref:System.Windows.Media.Stretch.Uniform> e la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà del secondo pennello è impostata su <xref:System.Windows.Media.Stretch.UniformToFill> .  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Nell'illustrazione seguente viene mostrato l'output del primo pennello, che ha un' <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione di <xref:System.Windows.Media.Stretch.Uniform> .  
  
 ![ImageBrush con allungamento Uniform](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 La figura seguente mostra l'output del secondo pennello, che ha un' <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione di <xref:System.Windows.Media.Stretch.UniformToFill> .  
  
 ![ImageBrush con allungamento UniformToFill](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Si noti che la proprietà si comporta in modo <xref:System.Windows.Media.TileBrush.Stretch%2A> identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, ovvero per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush> . Per altre informazioni su <xref:System.Windows.Media.ImageBrush> e sugli altri <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
 Si noti inoltre che, sebbene la <xref:System.Windows.Media.TileBrush.Stretch%2A> Proprietà appaia per specificare il modo in <xref:System.Windows.Media.TileBrush> cui il contenuto si adatta all'area di output, specifica effettivamente il modo in cui il contenuto viene <xref:System.Windows.Media.TileBrush> esteso per riempire la tessera di base. Per altre informazioni, vedere <xref:System.Windows.Media.TileBrush>.  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
