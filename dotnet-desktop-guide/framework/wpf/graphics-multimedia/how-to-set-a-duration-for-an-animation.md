---
title: "Procedura: impostare una durata per un'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969028"
---
# <a name="how-to-set-a-duration-for-an-animation"></a>Procedura: impostare una durata per un'animazione
Un oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza di tale segmento è determinata dall'oggetto della sequenza temporale <xref:System.Windows.Duration> . Quando <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata, la riproduzione viene interrotta. Se <xref:System.Windows.Media.Animation.Timeline> ha sequenze temporali figlio, si interrompe anche la riproduzione. Nel caso di un'animazione, l'oggetto <xref:System.Windows.Duration> specifica il tempo necessario per la transizione dell'animazione dal valore iniziale al valore finale.  
  
 È possibile specificare un oggetto <xref:System.Windows.Duration> con uno specifico, un'ora finita o i valori speciali <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A> . La durata di un'animazione deve essere sempre un valore di ora, perché un'animazione deve avere sempre una lunghezza definita e finita. in caso contrario, l'animazione non saprà come eseguire la transizione tra i valori di destinazione. Le sequenze temporali <xref:System.Windows.Media.Animation.TimelineGroup> del contenitore (oggetti), ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline> , hanno una durata predefinita <xref:System.Windows.Duration.Automatic%2A> , il che significa che terminano automaticamente quando l'ultimo figlio smette di essere riprodotto.  
  
 Nell'esempio seguente, la larghezza, l'altezza e il colore di riempimento di un oggetto <xref:System.Windows.Shapes.Rectangle> sono animati. Le durate sono impostate su animazioni e sequenze temporali del contenitore che comportano effetti di animazione, tra cui il controllo della velocità percepita di un'animazione e l'override della durata delle sequenze temporali figlio con la durata di una sequenza temporale del contenitore.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Duration>
- [Cenni preliminari sull'animazione](animation-overview.md)
