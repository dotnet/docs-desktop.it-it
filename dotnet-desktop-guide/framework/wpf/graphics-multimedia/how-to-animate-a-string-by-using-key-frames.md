---
title: 'Procedura: animare una stringa utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966121"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Procedura: animare una stringa utilizzando fotogrammi chiave
Questo esempio illustra come animare una stringa, che in questo esempio è la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un oggetto <xref:System.Windows.Controls.Button> .  
  
 Tutti i fotogrammi chiave in questo esempio usano un'istanza della <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione stringa creata con fotogrammi chiave può usare solo fotogrammi chiave discreti. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creare salti improvvisi tra i valori, ovvero le modifiche apportate all'animazione si verificano rapidamente e non sono impercettibili.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
