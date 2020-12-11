---
title: "Procedura: disegnare un'area con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963457"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Procedura: disegnare un'area con un'immagine
Questo esempio illustra come usare la <xref:System.Windows.Media.ImageBrush> classe per disegnare un'area con un'immagine. Un oggetto <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine, specificata dalla relativa <xref:System.Windows.Media.ImageBrush.ImageSource%2A> Proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene disegnato l'oggetto <xref:System.Windows.Controls.Control.Background%2A> di un pulsante utilizzando un oggetto <xref:System.Windows.Media.ImageBrush> .  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Per impostazione predefinita, un oggetto <xref:System.Windows.Media.ImageBrush> estende la propria immagine in modo da riempire completamente l'area che si sta disegnando. Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine. È possibile controllare questo comportamento impostando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di <xref:System.Windows.Media.TileBrush> su <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill> , che consente al pennello di mantenere le proporzioni dell'immagine.  
  
 Se si impostano le <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà e di un <xref:System.Windows.Media.ImageBrush> , è possibile creare un modello ripetuto. L'esempio seguente disegna un pulsante con un modello creato da un'immagine.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Per altre informazioni sulla <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
