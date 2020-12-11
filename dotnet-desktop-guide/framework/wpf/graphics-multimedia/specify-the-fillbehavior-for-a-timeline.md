---
title: 'Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965491"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Procedura: specificare la proprietà FillBehavior di un oggetto Timeline che ha raggiunto la fine del periodo di attività
In questo esempio viene illustrato come specificare <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> per l'oggetto inattivo <xref:System.Windows.Media.Animation.Timeline> di una proprietà animata.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà di un oggetto <xref:System.Windows.Media.Animation.Timeline> determina cosa accade al valore di una proprietà animata quando non viene animata, ovvero quando <xref:System.Windows.Media.Animation.Timeline> è inattivo, ma il padre <xref:System.Windows.Media.Animation.Timeline> è all'interno del periodo attivo o di attesa. Ad esempio, una proprietà animata rimane in corrispondenza del valore finale dopo che l'animazione termina o Ripristina il valore che aveva prima dell'avvio dell'animazione?  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare l'oggetto <xref:System.Windows.FrameworkElement.Width%2A> di due rettangoli. Ogni rettangolo utilizza un <xref:System.Windows.Media.Animation.Timeline> oggetto diverso.  
  
 Uno <xref:System.Windows.Media.Animation.Timeline> ha un oggetto <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> impostato su <xref:System.Windows.Media.Animation.FillBehavior.Stop> , che fa sì che la larghezza del rettangolo torni al valore non animato al termine dell'operazione <xref:System.Windows.Media.Animation.Timeline> . L'altro <xref:System.Windows.Media.Animation.Timeline> ha <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> , che fa sì che la larghezza rimanga al suo valore finale al termine dell'operazione <xref:System.Windows.Media.Animation.Timeline> .  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Per l'esempio completo, vedere [raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
