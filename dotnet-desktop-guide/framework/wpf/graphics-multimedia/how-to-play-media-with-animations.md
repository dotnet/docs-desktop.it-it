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
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="5bae0-102">Procedura: riprodurre contenuto multimediale con animazioni</span><span class="sxs-lookup"><span data-stu-id="5bae0-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="5bae0-103">Questo esempio illustra come riprodurre file multimediali e animazioni contemporaneamente usando le <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classi e nello stesso <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="5bae0-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bae0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5bae0-104">Example</span></span>  
 <span data-ttu-id="5bae0-105">È possibile usare uno o più <xref:System.Windows.Media.MediaTimeline> oggetti in un <xref:System.Windows.Media.Animation.Storyboard> insieme ad altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.</span><span class="sxs-lookup"><span data-stu-id="5bae0-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="5bae0-106">Nell'esempio seguente la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> proprietà di viene impostata <xref:System.Windows.Media.Animation.Storyboard> su un valore di `Slip` , che specifica che l'animazione non avanza fino a quando non viene progredito il supporto (video in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="5bae0-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="5bae0-107">Questa funzionalità potrebbe essere necessaria se la riproduzione multimediale viene ritardata a causa del tempo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="5bae0-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5bae0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bae0-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="5bae0-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="5bae0-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="5bae0-110">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="5bae0-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="5bae0-111">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="5bae0-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="5bae0-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="5bae0-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5bae0-113">Grafica e Multimedia</span><span class="sxs-lookup"><span data-stu-id="5bae0-113">Graphics and Multimedia</span></span>](index.md)
