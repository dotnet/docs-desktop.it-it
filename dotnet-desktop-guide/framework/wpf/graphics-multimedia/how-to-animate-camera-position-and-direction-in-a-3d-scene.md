---
title: 'Procedura: animare la posizione e la direzione di una fotocamera in una scena tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966898"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Procedura: animare la posizione e la direzione di una fotocamera in una scena tridimensionale
Nell'esempio seguente viene illustrato come animare la posizione di una fotocamera e animare la direzione in cui punta in una scena 3D. Questa operazione viene eseguita usando <xref:System.Windows.Media.Animation.Point3DAnimation> e <xref:System.Windows.Media.Animation.Vector3DAnimation> per animare <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> rispettivamente le <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> proprietà e di <xref:System.Windows.Media.Media3D.PerspectiveCamera> . È possibile utilizzare un'animazione simile alla seguente per modificare la visualizzazione di una scena in risposta a un evento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animare la posizione e la direzione di una fotocamera utilizzando i fotogrammi chiave](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
