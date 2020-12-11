---
title: 'Procedura: animare una proprietà utilizzando un oggetto AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952302"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Procedura: animare una proprietà utilizzando un oggetto AnimationClock
Questo esempio illustra come usare <xref:System.Windows.Media.Animation.Clock> gli oggetti per animare una proprietà.  
  
 Esistono tre modi per animare una proprietà di dipendenza:  
  
- Creare un oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> e associarlo a tale proprietà utilizzando un oggetto <xref:System.Windows.Media.Animation.Storyboard> .  
  
- Usare il metodo dell'oggetto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> per applicare un singolo oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> a una proprietà di destinazione.  
  
- Creare un oggetto <xref:System.Windows.Media.Animation.AnimationClock> da un oggetto <xref:System.Windows.Media.Animation.AnimationTimeline> e applicarlo a una proprietà.  
  
 <xref:System.Windows.Media.Animation.Storyboard> gli oggetti e il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo consentono di animare le proprietà senza creare e distribuire direttamente orologi (per alcuni esempi, vedere [animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md) e [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); gli orologi vengono creati e distribuiti automaticamente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a due proprietà simili.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Per un esempio che illustra come controllare in modo interattivo un oggetto <xref:System.Windows.Media.Animation.Clock> dopo l'avvio, vedere controllare in modo [interattivo un orologio](how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Vedere anche

- [Aggiungere un'animazione a una proprietà usando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)
- [Aggiungere un'animazione a una proprietà senza usare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md)
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
