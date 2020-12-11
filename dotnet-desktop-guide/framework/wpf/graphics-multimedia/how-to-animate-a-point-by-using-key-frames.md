---
title: 'Procedura: animare un punto utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967018"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Procedura: animare un punto utilizzando fotogrammi chiave
Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe per aggiungere un'animazione a <xref:System.Windows.Point> .  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un'ellisse lungo un tracciato triangolare. Nell'esempio viene utilizzata la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà di un oggetto <xref:System.Windows.Media.EllipseGeometry> . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante il primo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.LinearPointKeyFrame> classe per spostare l'ellisse lungo un tracciato a una velocità costante dalla posizione iniziale. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearPointKeyFrame> creare un'interpolazione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> classe per spostare improvvisamente l'ellisse lungo il percorso alla posizione successiva. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> creare salti improvvisi tra i valori.  
  
3. Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplinePointKeyFrame> classe per spostare nuovamente l'ellisse nella posizione iniziale. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplinePointKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> Proprietà. In questo esempio, l'animazione inizia a spostarsi lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> . Tuttavia, quando si applica un'unica animazione nel codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> . Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
