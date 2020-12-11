---
title: 'Procedura: animare le proprietà del materiale in una scena 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961096"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a><span data-ttu-id="cc729-102">Procedura: animare le proprietà del materiale in una scena 3D</span><span class="sxs-lookup"><span data-stu-id="cc729-102">How to: Animate Material Properties in a 3D Scene</span></span>
<span data-ttu-id="cc729-103">Questo esempio illustra come aggiungere un'animazione alla <xref:System.Windows.Media.Brush.Opacity%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="cc729-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>  
  
 <span data-ttu-id="cc729-104">Nell'esempio di codice seguente viene definito l' <xref:System.Windows.Media.LinearGradientBrush> oggetto utilizzato come <xref:System.Windows.Media.Media3D.Material> applicato all'oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="cc729-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="cc729-105">La <xref:System.Windows.Media.Brush.Opacity%2A> proprietà di questo oggetto <xref:System.Windows.Media.LinearGradientBrush> viene animata usando l'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="cc729-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="cc729-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc729-106">Example</span></span>  
 <span data-ttu-id="cc729-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="cc729-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cc729-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc729-108">See also</span></span>

- [<span data-ttu-id="cc729-109">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="cc729-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="cc729-110">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="cc729-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
