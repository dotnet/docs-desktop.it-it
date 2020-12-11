---
title: 'Procedura: animare una rotazione 3D utilizzando gli storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967030"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>Procedura: animare una rotazione 3D utilizzando gli storyboard
Nell'esempio seguente viene illustrato come fare in modo che un oggetto 3D ruoti mentre "oscilla" animando <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> le <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà e di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto. Questo <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D, quindi l'animazione delle proprietà crea l'effetto di rotazione desiderato. All'interno dello storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene usato per aggiungere un'animazione alla <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Proprietà mentre <xref:System.Windows.Media.Animation.Vector3DAnimation> viene usato per aggiungere un'animazione alla <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare una rotazione 3D usando Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
