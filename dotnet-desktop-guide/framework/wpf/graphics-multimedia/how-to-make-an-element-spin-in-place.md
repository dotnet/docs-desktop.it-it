---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969877"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Procedura: far ruotare sul posto un elemento
In questo esempio viene illustrato come eseguire la rotazione di un elemento utilizzando un oggetto <xref:System.Windows.Media.RotateTransform> e un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> .  
  
 Nell'esempio seguente viene applicato alla <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento. Nell'esempio viene utilizzato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare l'oggetto <xref:System.Windows.Media.RotateTransform.Angle%2A> di <xref:System.Windows.Media.RotateTransform> . Per far ruotare l'elemento, nell'esempio viene impostata la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento sul punto (0,5, 0,5).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Per l'esempio completo, che include altri esempi di trasformazione, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
