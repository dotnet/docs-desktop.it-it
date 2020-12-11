---
title: 'Procedura: animare un rettangolo utilizzando fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952301"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Procedura: animare un rettangolo utilizzando fotogrammi chiave
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un oggetto utilizzando <xref:System.Windows.Media.RectangleGeometry> fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> classe per aggiungere un'animazione alla <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un oggetto <xref:System.Windows.Media.RectangleGeometry> . Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, usa un'istanza della <xref:System.Windows.Media.Animation.LinearRectKeyFrame> classe per aggiungere un'animazione a una modifica graduale della posizione, della larghezza e dell'altezza di un rettangolo. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearRectKeyFrame> creare una transizione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo, usa un'istanza della <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> classe per ridurre improvvisamente l'altezza del rettangolo. I fotogrammi chiave discreti <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> , ad esempio, creano modifiche improvvise tra i valori, ovvero la riduzione dell'altezza si verifica rapidamente e non è un'operazione impercettibile.  
  
3. Durante i due secondi finali, usa un'istanza della <xref:System.Windows.Media.Animation.SplineRectKeyFrame> classe per ripristinare le dimensioni e la posizione originali del rettangolo. Fotogrammi chiave spline come <xref:System.Windows.Media.Animation.SplineRectKeyFrame> creare una transizione variabile tra i valori in base ai valori della <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> Proprietà. In questo esempio l'animazione inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
