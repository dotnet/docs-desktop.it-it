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
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="002f4-102">Procedura: animare una rotazione 3D utilizzando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="002f4-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="002f4-103">Nell'esempio seguente viene illustrato come fare in modo che un oggetto 3D ruoti mentre "oscilla" animando <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> le <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà e di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto.</span><span class="sxs-lookup"><span data-stu-id="002f4-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="002f4-104">Questo <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D, quindi l'animazione delle proprietà crea l'effetto di rotazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="002f4-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="002f4-105">All'interno dello storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene usato per aggiungere un'animazione alla <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Proprietà mentre <xref:System.Windows.Media.Animation.Vector3DAnimation> viene usato per aggiungere un'animazione alla <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="002f4-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="002f4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="002f4-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="002f4-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="002f4-107">See also</span></span>

- [<span data-ttu-id="002f4-108">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="002f4-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="002f4-109">Animare una rotazione 3D usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="002f4-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="002f4-110">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="002f4-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="002f4-111">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="002f4-111">Storyboards Overview</span></span>](storyboards-overview.md)
