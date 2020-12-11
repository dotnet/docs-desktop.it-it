---
title: 'Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960808"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="14215-102">Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="14215-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="14215-103">Nell'esempio seguente viene illustrato come applicare un oggetto <xref:System.Windows.Media.Media3D.Material> alla parte anteriore e posteriore di un oggetto 3D e animare l'oggetto per visualizzare entrambi i lati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="14215-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="14215-104">La <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D> oggetto viene utilizzata per applicare un oggetto rosso <xref:System.Windows.Media.Brush> al lato anteriore dell'oggetto e la <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> viene utilizzata per applicare un blu <xref:System.Windows.Media.Brush> al lato posteriore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="14215-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="14215-105">Il codice seguente illustra l'applicazione dei materiali all'oggetto:</span><span class="sxs-lookup"><span data-stu-id="14215-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="14215-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="14215-106">Example</span></span>  
 <span data-ttu-id="14215-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="14215-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="14215-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14215-108">See also</span></span>

- [<span data-ttu-id="14215-109">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="14215-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="14215-110">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="14215-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="14215-111">Animare le proprietà Material in una scena 3D</span><span class="sxs-lookup"><span data-stu-id="14215-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="14215-112">Applicare EmissiveMaterial a un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="14215-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
