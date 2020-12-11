---
title: 'Procedura: animare una rotazione 3D utilizzando quaternioni'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967042"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>Procedura: animare una rotazione 3D utilizzando quaternioni
Questo esempio illustra come aggiungere un'animazione a una rotazione di un oggetto 3D usando i quaternioni.  
  
 Il codice seguente mostra un oggetto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> usato come valore per la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un oggetto <xref:System.Windows.Media.Media3D.RotateTransform3D> .  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Questa operazione <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene animata con un oggetto <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un oggetto <xref:System.Windows.Media.Animation.Storyboard> usando il codice riportato di seguito.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Animare una rotazione 3D usando gli storyboard](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
