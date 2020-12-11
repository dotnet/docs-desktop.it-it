---
title: 'Procedura: specificare HandoffBehavior tra le animazioni storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961285"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Procedura: specificare HandoffBehavior tra le animazioni storyboard
Questo esempio illustra come specificare il comportamento uniforme tra le animazioni dello storyboard. La <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà di <xref:System.Windows.Media.Animation.BeginStoryboard> specifica il modo in cui le nuove animazioni interagiscono con quelle esistenti già applicate a una proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati due pulsanti che ingrandiscono quando il cursore del mouse viene spostato su di essi e diventano più piccoli quando si sposta il cursore. Se si passa il mouse su un pulsante e quindi si rimuove rapidamente il cursore, la seconda animazione verrà applicata prima del completamento della prima. Quando due animazioni si sovrappongono come questa, è possibile vedere la differenza tra i <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> . Il valore <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte che provocano una transizione più uniforme tra le animazioni mentre un valore <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione sostituisca immediatamente l'animazione sovrapposta precedente.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
