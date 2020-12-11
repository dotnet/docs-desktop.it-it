---
title: 'Procedura: accumulare valori di animazione durante i cicli ripetuti'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968194"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Procedura: accumulare valori di animazione durante i cicli ripetuti
Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di animazione nei cicli ripetuti.  
  
## <a name="example"></a>Esempio  
 Utilizzare la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà per accumulare i valori di base di un'animazione nei cicli ripetuti. Se ad esempio si imposta un'animazione su Ripeti 9 volte ( <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") e si imposta la proprietà su animate tra 10 e 15 (da = 10 a = 15), la proprietà aggiunge un'animazione da 10 a 15 durante il primo ciclo, da 15 a 20 durante il secondo ciclo, da 20 a 25 durante il terzo ciclo e così via. Di conseguenza, ogni ciclo di animazione usa il valore di animazione finale del ciclo di animazione precedente come valore di base.  
  
 È possibile usare la `IsCumulative` proprietà con la maggior parte delle animazioni di base e la maggior parte delle animazioni fotogrammi chiave. Per altre informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 Nell'esempio seguente viene illustrato questo comportamento animando la larghezza di quattro rettangoli. Esempio:  
  
- Aggiunge un'animazione al primo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà su `true` .  
  
- Aggiunge un'animazione al secondo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimation> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> proprietà sul valore predefinito di `false` .  
  
- Aggiunge un'animazione al terzo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà su `true` .  
  
- Aggiunge un'animazione all'ultimo rettangolo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> e imposta la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> proprietà su `false` .  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [Ripetere un'animazione](how-to-repeat-an-animation.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure](animation-and-timing-how-to-topics.md)
