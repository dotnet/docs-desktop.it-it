---
title: 'Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio'
ms.date: 03/30/2017
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
ms.openlocfilehash: 21a297208be045eea79d6f5ca6c8eac016d26345
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961294"
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio
Questo esempio illustra come semplificare le animazioni usando oggetti figlio <xref:System.Windows.Media.Animation.ParallelTimeline> . Un <xref:System.Windows.Media.Animation.Storyboard> è un tipo di <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni di destinazione per le sequenze temporali in essa contenute. Usare un <xref:System.Windows.Media.Animation.Storyboard> oggetto per fornire informazioni sulla sequenza temporale, incluse le informazioni su oggetti e proprietà.  
  
 Per iniziare un'animazione, usare uno o più <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti come elementi figlio annidati di un oggetto <xref:System.Windows.Media.Animation.Storyboard> . Questi <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti possono contenere altre animazioni e pertanto possono incapsulare meglio le sequenze temporali in animazioni complesse. Se ad esempio si sta aggiungendo un'animazione a <xref:System.Windows.Controls.TextBlock> e diverse forme nello stesso <xref:System.Windows.Media.Animation.Storyboard> , è possibile separare le animazioni per le <xref:System.Windows.Controls.TextBlock> forme e, inserendo ognuna in un separato <xref:System.Windows.Media.Animation.ParallelTimeline> . Poiché ogni <xref:System.Windows.Media.Animation.ParallelTimeline> elemento ha un proprio <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> e tutti gli elementi figlio dell'oggetto <xref:System.Windows.Media.Animation.ParallelTimeline> Begin rispetto a questo <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> , l'intervallo è incapsulato in modo migliore.  
  
 Nell'esempio seguente vengono animate due parti di testo ( <xref:System.Windows.Controls.TextBlock> oggetti) dall'interno dello stesso oggetto <xref:System.Windows.Media.Animation.Storyboard> . Un oggetto <xref:System.Windows.Media.Animation.ParallelTimeline> incapsula le animazioni di uno degli <xref:System.Windows.Controls.TextBlock> oggetti.  
  
 **Nota sulle prestazioni:** Sebbene sia possibile annidare le <xref:System.Windows.Media.Animation.Storyboard> sequenze temporali tra loro, le istanze <xref:System.Windows.Media.Animation.ParallelTimeline> di sono più adatte per l'annidamento perché richiedono un minor overhead. (La <xref:System.Windows.Media.Animation.Storyboard> classe eredita dalla <xref:System.Windows.Media.Animation.ParallelTimeline> classe).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Specificare HandoffBehavior tra le animazioni storyboard](how-to-specify-handoffbehavior-between-storyboard-animations.md)
