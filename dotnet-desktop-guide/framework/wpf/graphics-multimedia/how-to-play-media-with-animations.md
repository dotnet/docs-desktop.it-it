---
title: 'Procedura: riprodurre contenuto multimediale con animazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960805"
---
# <a name="how-to-play-media-with-animations"></a>Procedura: riprodurre contenuto multimediale con animazioni
Questo esempio illustra come riprodurre file multimediali e animazioni contemporaneamente usando le <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classi e nello stesso <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>Esempio  
 È possibile usare uno o più <xref:System.Windows.Media.MediaTimeline> oggetti in un <xref:System.Windows.Media.Animation.Storyboard> insieme ad altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.  
  
 Nell'esempio seguente la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> proprietà di viene impostata <xref:System.Windows.Media.Animation.Storyboard> su un valore di `Slip` , che specifica che l'animazione non avanza fino a quando non viene progredito il supporto (video in questo esempio). Questa funzionalità potrebbe essere necessaria se la riproduzione multimediale viene ritardata a causa del tempo di caricamento.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [Procedure](audio-and-video-how-to-topics.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e Multimedia](index.md)
