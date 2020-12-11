---
title: 'Procedura: inclinare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961291"
---
# <a name="how-to-skew-an-element"></a>Procedura: inclinare un elemento
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.SkewTransform> per inclinare un elemento. L'inclinazione, nota anche come distorsione, è una trasformazione che adatta lo spazio delle coordinate in modo non uniforme. Un utilizzo tipico di un oggetto <xref:System.Windows.Media.SkewTransform> è per la simulazione della profondità 3D negli oggetti 2D.  
  
 Usare le <xref:System.Windows.Media.SkewTransform.CenterX%2A> <xref:System.Windows.Media.SkewTransform.CenterY%2A> proprietà e per specificare il punto centrale di <xref:System.Windows.Media.SkewTransform> .  
  
 Usare le <xref:System.Windows.Media.SkewTransform.AngleX%2A> <xref:System.Windows.Media.SkewTransform.AngleY%2A> proprietà e per specificare l'angolo di inclinazione dell'asse x e l'asse y e per inclinare il sistema di coordinate corrente lungo questi assi.  
  
 Per stimare l'effetto di una trasformazione asimmetria, tenere presente che <xref:System.Windows.Media.SkewTransform.AngleX%2A> inclina i valori dell'asse x rispetto al sistema di coordinate originale. Pertanto, per un valore <xref:System.Windows.Media.SkewTransform.AngleX%2A> pari a 30, l'asse y ruota di 30 gradi attraverso l'origine e inclina i valori in x-by 30 gradi da tale origine. Analogamente, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> valore pari a 30 inclina i valori y della forma di 30 gradi dall'origine. Si noti che non si tratta dello stesso effetto ottenuto traslando (spostando) il sistema di coordinate di 30 gradi nell'asse x o y.  
  
 Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (0,0).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25, 25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 L'esempio seguente applica un'inclinazione verticale di 45 gradi a un oggetto <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25, 25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La figura seguente illustra le diverse inclinazioni usate in questo esempio.  
  
 ![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
I tre esempi SkewTransform illustrati  
  
 Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
