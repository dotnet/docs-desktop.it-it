---
title: 'Procedura: animare una rotazione 3D mediante fotogrammi chiave (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968092"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Procedura: animare una rotazione 3D mediante fotogrammi chiave (QuaternionAnimationUsingKeyFrames)
Nell'esempio seguente <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> viene usato per fare in modo che un oggetto 3D ruoti. Questa animazione usa i fotogrammi chiave seguenti:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> viene usato per creare un'interpolazione lineare uniforme tra i valori.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> viene usato per creare "salti" improvvisi tra valori (nessuna interpolazione).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> viene usato per creare una transizione variabile tra i valori a seconda della <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Proprietà. Nell'esempio seguente questa parte dell'animazione inizia con lentezza ma verso la fine del segmento di tempo, accelera in modo esponenziale.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare una rotazione 3D usando gli storyboard](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare una rotazione 3D usando i quaternioni](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
