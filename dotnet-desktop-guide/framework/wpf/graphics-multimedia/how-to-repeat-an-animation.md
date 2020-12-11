---
title: "Procedura: ripetere un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969271"
---
# <a name="how-to-repeat-an-animation"></a>Procedura: ripetere un'animazione
Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un oggetto per <xref:System.Windows.Media.Animation.Timeline> controllare il comportamento di ripetizione di un'animazione.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> controllo determina il numero di volte in cui un'animazione ripete la durata normale. Usando <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , è possibile specificare che un oggetto si <xref:System.Windows.Media.Animation.Timeline> ripete per un determinato numero di volte (un conteggio delle iterazioni) o per un periodo di tempo specificato. In entrambi i casi, l'animazione passa attraverso il numero di esecuzioni da inizio a fine necessarie per riempire il numero o la durata richiesta.  
  
 Per impostazione predefinita, le sequenze temporali hanno un numero di ripetizioni di 1,0, che significa che vengono riprodotte una sola volta e non vengono ripetute. Tuttavia, se si imposta la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà di un <xref:System.Windows.Media.Animation.Timeline> su <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> , la sequenza temporale si ripete a tempo indefinito.  
  
 Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> proprietà per controllare il comportamento di ripetizione di un'animazione. Nell'esempio viene animata la <xref:System.Windows.FrameworkElement.Width%2A> proprietà di cinque rettangoli con ogni rettangolo utilizzando un tipo diverso di comportamento di ripetizione.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Per l'esempio completo, vedere [esempio di comportamento della temporizzazione delle animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).  
  
## <a name="see-also"></a>Vedere anche

- [Accumulare valori di animazione durante i cicli ripetuti](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Specificare se una sequenza temporale viene invertita automaticamente](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Esempio di comportamento temporale di un'animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
