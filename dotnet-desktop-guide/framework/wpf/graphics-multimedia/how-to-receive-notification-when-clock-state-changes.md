---
title: "Procedura: ricevere una notifica quando uno stato dell'orologio viene modificato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: dc3fffb88ce59ceb908d6febd2f078820513b641
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960793"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a>Procedura: ricevere una notifica quando uno stato dell'orologio viene modificato
Un evento del clock <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> si verifica quando <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> non è più valido, ad esempio quando l'orologio viene avviato o arrestato. È possibile eseguire la registrazione per questo evento usando direttamente un <xref:System.Windows.Media.Animation.Clock> oppure è possibile eseguire la registrazione usando un <xref:System.Windows.Media.Animation.Timeline> .  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> vengono utilizzati un oggetto e due <xref:System.Windows.Media.Animation.DoubleAnimation> oggetti per aggiungere un'animazione alla larghezza di due rettangoli. L' <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene usato per restare in ascolto delle modifiche dello stato dell'orologio.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 Nella figura seguente vengono illustrati i diversi stati immessi dalle animazioni durante l'avanzamento della sequenza temporale padre (*storyboard*).  
  
 ![Stati di clock per uno storyboard con due animazioni](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 La tabella seguente mostra l'ora in cui viene generato l'evento di *Animazione1* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> :  
  
||||||||  
|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|10|19|21|30|39|  
|Stato|Attivo|Attivo|Arrestato|Attivo|Attivo|Arrestato|  
  
 La tabella seguente mostra l'ora in cui viene generato l'evento di *Animation2* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> :  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Tempo (secondi)|1|9|11|19|21|29|31|39|  
|Stato|Attivo|Riempimento|Attivo|Arrestato|Attivo|Riempimento|Attivo|Arrestato|  
  
 Si noti che l'evento di *Animazione1* viene  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> generato a 10 secondi, anche se il relativo stato rimane <xref:System.Windows.Media.Animation.ClockState.Active> . Questo perché lo stato è cambiato a 10 secondi, ma è stato modificato da <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> e quindi di nuovo a <xref:System.Windows.Media.Animation.ClockState.Active> nello stesso segno di uguale.
