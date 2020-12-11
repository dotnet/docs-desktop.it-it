---
title: 'Procedura: animare un oggetto Double utilizzando i fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967024"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Procedura: animare un oggetto Double utilizzando i fotogrammi chiave
In questo esempio viene illustrato come animare il valore di una proprietà che accetta un oggetto utilizzando <xref:System.Double> fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un rettangolo in una schermata. Nell'esempio viene utilizzata la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di un oggetto <xref:System.Windows.Media.TranslateTransform> applicato a un oggetto <xref:System.Windows.Shapes.Rectangle> . Questa animazione, ripetuta all'infinito, usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi tre secondi, usa un'istanza della <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> classe per spostare il rettangolo lungo un tracciato a una velocità costante dalla posizione iniziale alla posizione 500. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2. Alla fine del quarto secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> classe per spostare improvvisamente il rettangolo nella posizione successiva. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> creare salti improvvisi tra i valori. In questo esempio, il rettangolo si trova in corrispondenza della posizione iniziale e improvvisamente appare nella posizione 500.  
  
3. Nei due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> classe per spostare nuovamente il rettangolo nella posizione iniziale. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> creare una transizione variabile tra i valori in base al valore della <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> Proprietà. In questo esempio, il rettangolo inizia a spostarsi lentamente e quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> . In alternativa, quando si applica un'unica animazione nel codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> . Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
