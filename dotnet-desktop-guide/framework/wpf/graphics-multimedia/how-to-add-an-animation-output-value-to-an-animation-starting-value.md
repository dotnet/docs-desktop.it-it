---
title: "Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960862"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Procedura: aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione
Questo esempio illustra come aggiungere un valore di output dell'animazione a un valore iniziale dell'animazione.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà specifica se si desidera che il valore di output di un'animazione venga aggiunto al valore iniziale (valore di base) di una proprietà animata. È possibile usare la <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> proprietà con la maggior parte delle animazioni di base e la maggior parte delle animazioni fotogrammi chiave. Per altre informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md) e [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 Nell'esempio seguente viene illustrato l'effetto dell'utilizzo della <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimation> e utilizzando la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> proprietà con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> .  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Accumulare valori di animazione durante i cicli ripetuti](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
