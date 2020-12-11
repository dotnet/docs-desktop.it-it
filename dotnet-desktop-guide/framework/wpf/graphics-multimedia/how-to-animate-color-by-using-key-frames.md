---
title: 'Procedura: animare il colore utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968086"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Procedura: animare il colore utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare l'oggetto <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un oggetto <xref:System.Windows.Media.SolidColorBrush> . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, usa un'istanza della <xref:System.Windows.Media.Animation.LinearColorKeyFrame> classe per modificare gradualmente il colore da verde a rosso. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearColorKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> classe per modificare rapidamente il colore da rosso a giallo. I fotogrammi chiave discreti <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> , ad esempio, creano modifiche improvvise tra i valori, ovvero la modifica del colore in questa parte dell'animazione viene eseguita rapidamente e non è sottile.  
  
3. Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineColorKeyFrame> classe per modificare di nuovo il colore, questa volta da giallo a verde. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineColorKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> Proprietà. In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
