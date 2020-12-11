---
title: 'Procedura: animare un valore Boolean utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967027"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a>Procedura: animare un valore Boolean utilizzando fotogrammi chiave
Questo esempio illustra come animare il valore booleano della proprietà di un <xref:System.Windows.Controls.Button> controllo usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.UIElement.IsEnabled%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo. Tutti i fotogrammi chiave in questo esempio usano un'istanza della <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> classe. I fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> creare salti improvvisi tra i valori, ovvero lo spostamento dell'animazione sono di tipo Jerky.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
