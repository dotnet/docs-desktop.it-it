---
title: 'Procedura: animare un rettangolo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966133"
---
# <a name="how-to-animate-a-rectangle"></a>Procedura: animare un rettangolo
Questo esempio illustra come animare le modifiche apportate alle dimensioni e alla posizione di un rettangolo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata un'istanza della <xref:System.Windows.Media.Animation.RectAnimation> classe per aggiungere un'animazione alla <xref:System.Windows.Media.RectangleGeometry.Rect%2A> proprietà di un oggetto <xref:System.Windows.Media.RectangleGeometry> , che aggiunge un'animazione alle dimensioni e alla posizione del rettangolo.  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e Multimedia](index.md)
- [Procedure relative alle funzionalità grafiche](graphics-how-to-topics.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
