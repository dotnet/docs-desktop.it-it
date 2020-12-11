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
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="72740-102">Procedura: animare una rotazione 3D utilizzando quaternioni</span><span class="sxs-lookup"><span data-stu-id="72740-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="72740-103">Questo esempio illustra come aggiungere un'animazione a una rotazione di un oggetto 3D usando i quaternioni.</span><span class="sxs-lookup"><span data-stu-id="72740-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="72740-104">Il codice seguente mostra un oggetto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> usato come valore per la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un oggetto <xref:System.Windows.Media.Media3D.RotateTransform3D> .</span><span class="sxs-lookup"><span data-stu-id="72740-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="72740-105">Questa operazione <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene animata con un oggetto <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un oggetto <xref:System.Windows.Media.Animation.Storyboard> usando il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="72740-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="72740-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="72740-106">Example</span></span>  
 <span data-ttu-id="72740-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="72740-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="72740-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72740-108">See also</span></span>

- [<span data-ttu-id="72740-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="72740-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="72740-110">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="72740-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="72740-111">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="72740-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="72740-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="72740-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="72740-113">Animare una rotazione 3D usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="72740-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="72740-114">Animare una rotazione 3D usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="72740-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
