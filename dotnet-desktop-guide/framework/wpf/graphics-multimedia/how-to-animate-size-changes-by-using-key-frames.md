---
title: 'Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961108"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Procedura: animare le modifiche di dimensione utilizzando fotogrammi chiave
Questo esempio mostra come animare le modifiche di dimensione usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.ArcSegment.Size%2A> proprietà di un oggetto <xref:System.Windows.Media.ArcSegment> . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante il primo mezzo secondo dell'animazione, usa un'istanza della <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> classe per aumentare gradualmente la dimensione dell'arco. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> classe per aumentare improvvisamente la dimensione dell'arco. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> creare salti improvvisi tra i valori, ovvero le modifiche delle dimensioni si verificano improvvisamente e non sono impercettibili.  
  
3. Nei due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> classe per aumentare la dimensione dell'arco. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> Proprietà. In questo esempio la dimensione dell'arco aumenta lentamente all'inizio e quindi aumenta in misura esponenziale verso la fine dell'intervallo di tempo.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
