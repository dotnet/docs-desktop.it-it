---
title: 'Procedura: animare un valore BorderThickness'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969532"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Procedura: animare un valore BorderThickness
Questo esempio illustra come animare le modifiche allo spessore di un bordo usando la <xref:System.Windows.Media.Animation.ThicknessAnimation> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene animato lo spessore di un bordo usando <xref:System.Windows.Media.Animation.ThicknessAnimation> . Nell'esempio viene utilizzata la <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà di <xref:System.Windows.Controls.Border> .  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Per l'esempio completo, vedere [raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Aggiungere un'animazione allo spessore di un bordo usando i fotogrammi chiave](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
