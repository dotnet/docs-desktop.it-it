---
title: 'Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966406"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="1bb2e-102">Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="1bb2e-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="1bb2e-103">Per riprodurre un file audio o video, è possibile usare un oggetto <xref:System.Windows.Media.VideoDrawing> e un oggetto <xref:System.Windows.Media.MediaPlayer> .</span><span class="sxs-lookup"><span data-stu-id="1bb2e-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="1bb2e-104">È possibile caricare e riprodurre contenuti multimediali in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-104">There are two ways to load and play media.</span></span> <span data-ttu-id="1bb2e-105">Il primo consiste nell'usare un oggetto <xref:System.Windows.Media.MediaPlayer> e un <xref:System.Windows.Media.VideoDrawing> autonomo e il secondo modo consiste nel creare un oggetto personalizzato <xref:System.Windows.Media.MediaTimeline> da usare con <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> .</span><span class="sxs-lookup"><span data-stu-id="1bb2e-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bb2e-106">Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="1bb2e-107">È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb2e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb2e-108">Example</span></span>  
 <span data-ttu-id="1bb2e-109">Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Media.VideoDrawing> e un oggetto <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="1bb2e-110">Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare un oggetto <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.MediaPlayer> gli <xref:System.Windows.Media.VideoDrawing> oggetti e.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="1bb2e-111"><xref:System.Windows.Media.MediaTimeline>Consente di specificare se il video deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb2e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb2e-112">Example</span></span>  
 <span data-ttu-id="1bb2e-113">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.MediaTimeline> con gli <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> oggetti e per riprodurre un video ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="1bb2e-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="1bb2e-114">Si noti che, quando si usa un <xref:System.Windows.Media.MediaTimeline> , si usa l'elemento interattivo <xref:System.Windows.Media.Animation.ClockController> restituito dalla <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di <xref:System.Windows.Media.MediaClock> per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer> .</span><span class="sxs-lookup"><span data-stu-id="1bb2e-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb2e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bb2e-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="1bb2e-116">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="1bb2e-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
