---
title: 'Procedura: animare una rotazione 3D mediante fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963466"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a><span data-ttu-id="2d054-102">Procedura: animare una rotazione 3D mediante fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="2d054-102">How to: Animate a 3D Rotation Using Key Frames</span></span>
<span data-ttu-id="2d054-103">Nell'esempio seguente <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> viene usato per fare in modo che un oggetto 3D ruoti mentre l'asse di rotazione anima il risultato di una "oscillazione".</span><span class="sxs-lookup"><span data-stu-id="2d054-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="2d054-104">Questa animazione usa i fotogrammi chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d054-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="2d054-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> viene usato per creare un'interpolazione lineare uniforme tra i valori.</span><span class="sxs-lookup"><span data-stu-id="2d054-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="2d054-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> viene usato per creare "salti" improvvisi tra valori (nessuna interpolazione).</span><span class="sxs-lookup"><span data-stu-id="2d054-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="2d054-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> viene usato per creare una transizione variabile tra i valori a seconda della <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d054-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2d054-108">Nell'esempio seguente questa parte dell'animazione inizia con lentezza ma verso la fine del segmento di tempo, accelera in modo esponenziale.</span><span class="sxs-lookup"><span data-stu-id="2d054-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d054-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d054-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2d054-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d054-110">See also</span></span>

- [<span data-ttu-id="2d054-111">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="2d054-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2d054-112">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="2d054-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="2d054-113">Animare una rotazione 3D usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="2d054-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="2d054-114">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="2d054-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="2d054-115">Animare una rotazione 3D usando i quaternioni</span><span class="sxs-lookup"><span data-stu-id="2d054-115">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="2d054-116">Animare una rotazione 3D usando i fotogrammi chiave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="2d054-116">Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
