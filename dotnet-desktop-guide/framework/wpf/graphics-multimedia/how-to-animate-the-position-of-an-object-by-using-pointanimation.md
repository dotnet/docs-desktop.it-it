---
title: 'Procedura: animare la posizione di un oggetto utilizzando PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960856"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Procedura: animare la posizione di un oggetto utilizzando PointAnimation
Questo esempio illustra come usare la <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un oggetto <xref:System.Windows.Shapes.Path> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene spostata un'ellisse lungo un oggetto <xref:System.Windows.Shapes.Path> da un punto sullo schermo a un altro. Nell'esempio viene animata la posizione di un oggetto <xref:System.Windows.Media.EllipseGeometry> utilizzando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione alla <xref:System.Windows.Media.EllipseGeometry.Center%2A> Proprietà.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e Multimedia](index.md)
- [Procedure relative alle funzionalità grafiche](graphics-how-to-topics.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
