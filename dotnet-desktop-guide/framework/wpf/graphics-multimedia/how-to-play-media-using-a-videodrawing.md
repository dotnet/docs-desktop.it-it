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
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing
Per riprodurre un file audio o video, è possibile usare un oggetto <xref:System.Windows.Media.VideoDrawing> e un oggetto <xref:System.Windows.Media.MediaPlayer> . È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un oggetto <xref:System.Windows.Media.MediaPlayer> e un <xref:System.Windows.Media.VideoDrawing> autonomo e il secondo modo consiste nel creare un oggetto personalizzato <xref:System.Windows.Media.MediaTimeline> da usare con <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> .  
  
> [!NOTE]
> Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati un oggetto <xref:System.Windows.Media.VideoDrawing> e un oggetto <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare un oggetto <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.MediaPlayer> gli <xref:System.Windows.Media.VideoDrawing> oggetti e. <xref:System.Windows.Media.MediaTimeline>Consente di specificare se il video deve essere ripetuto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.MediaTimeline> con gli <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> oggetti e per riprodurre un video ripetutamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa un <xref:System.Windows.Media.MediaTimeline> , si usa l'elemento interattivo <xref:System.Windows.Media.Animation.ClockController> restituito dalla <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di <xref:System.Windows.Media.MediaClock> per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VideoDrawing>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
