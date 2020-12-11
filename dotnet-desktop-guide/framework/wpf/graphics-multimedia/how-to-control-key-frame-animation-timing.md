---
title: 'Procedura: controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968056"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Procedura: controllare la durata delle animazioni con fotogrammi chiave

Questo esempio illustra come controllare l'intervallo dei fotogrammi chiave all'interno di un'animazione con fotogrammi chiave. Analogamente ad altre animazioni, le animazioni con fotogrammi chiave hanno una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Proprietà. Oltre a specificare la durata di un'animazione, è necessario specificare la parte di tale durata assegnata a ognuno dei fotogrammi chiave. Per assegnare l'ora, specificare un <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave nell'animazione.

<xref:System.Windows.Media.Animation.KeyTime>Per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica l'intervallo di tempo in cui un fotogramma chiave viene riprodotto). È possibile specificare <xref:System.Windows.Media.Animation.KeyTime> come <xref:System.TimeSpan> valore, come percentuale, o come <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valore speciale.

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> per animare un rettangolo sullo schermo. Gli orari delle chiavi dei fotogrammi chiave vengono impostati con <xref:System.TimeSpan> i valori.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

Nell'esempio seguente viene illustrata un'animazione identica, ad eccezione del fatto che le chiavi temporali dei fotogrammi chiave sono impostate con valori percentuali.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

Nell'esempio seguente vengono usati <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> i valori della chiave temporale.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3,3, 6,6 e 9,9 secondi](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

Nell'esempio finale vengono usati <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> i valori della chiave temporale.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

Nella figura seguente viene illustrato quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 0, 5 e 10 secondi](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

Per semplicità, le versioni del codice di questo esempio usano animazioni locali, non Storyboard, perché solo una singola animazione viene applicata a una singola proprietà, ma gli esempi possono essere modificati per usare gli storyboard. Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md).

Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation). Per ulteriori informazioni sulle animazioni con fotogramma chiave, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure](animation-and-timing-how-to-topics.md)
