---
title: 'Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961273"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno
La proprietà di una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> determina se viene riprodotta in senso inverso dopo il completamento di un'iterazione in attesa. Nell'esempio seguente vengono illustrate diverse animazioni con valori di durata e destinazione identici, ma con <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni diverse. Per illustrare il comportamento della <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà con impostazioni diverse <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni sono impostate per la ripetizione. Nell'ultima animazione viene illustrato il <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> funzionamento della proprietà sulle sequenze temporali nidificate.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
