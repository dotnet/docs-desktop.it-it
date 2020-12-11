---
title: 'Procedura: trasformare un oggetto Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965566"
---
# <a name="how-to-transform-a-brush"></a>Procedura: trasformare un oggetto Brush
Questo esempio illustra come trasformare <xref:System.Windows.Media.Brush> oggetti usando le due proprietà di trasformazione seguenti: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> .  
  
 Negli esempi seguenti viene usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare il contenuto di un oggetto <xref:System.Windows.Media.ImageBrush> di 45 gradi.  
  
 Nella figura seguente viene illustrato l'oggetto <xref:System.Windows.Media.ImageBrush> senza un oggetto <xref:System.Windows.Media.RotateTransform> , con l'oggetto <xref:System.Windows.Media.RotateTransform> applicato alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con l'oggetto <xref:System.Windows.Media.RotateTransform> applicato alla <xref:System.Windows.Media.Brush.Transform%2A> Proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Esempio  
 Nel primo esempio viene applicato un oggetto <xref:System.Windows.Media.RotateTransform> alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un oggetto <xref:System.Windows.Media.ImageBrush> . Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e di un <xref:System.Windows.Media.RotateTransform> oggetto sono entrambe impostate su 0,5, ovvero sulla coordinata relativa del punto centrale di questo contenuto. Di conseguenza, il <xref:System.Windows.Media.ImageBrush> contenuto ruota attorno al centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Nel secondo esempio viene anche applicato un oggetto <xref:System.Windows.Media.RotateTransform> a un oggetto. <xref:System.Windows.Media.ImageBrush> tuttavia, in questo esempio viene utilizzata la <xref:System.Windows.Media.Brush.Transform%2A> proprietà anziché la <xref:System.Windows.Media.Brush.RelativeTransform%2A> Proprietà.  
  
 Per ruotare il pennello intorno al relativo centro, l'esempio imposta <xref:System.Windows.Media.RotateTransform.CenterX%2A> le <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e dell' <xref:System.Windows.Media.RotateTransform> oggetto su coordinate assolute. Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Per una descrizione del funzionamento delle <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> proprietà e, vedere [Cenni preliminari sulla trasformazione dei pennelli](brush-transformation-overview.md).  
  
 Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle proprietà di trasformazione Brush](brush-transformation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
