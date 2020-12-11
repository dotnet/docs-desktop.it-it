---
title: 'Procedura: applicare materiale emissivo a un oggetto 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968488"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="7c57d-102">Procedura: applicare materiale emissivo a un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="7c57d-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="7c57d-103">Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Media.Media3D.EmissiveMaterial> per aggiungere colore a un materiale esistente uguale al colore del pennello del EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="7c57d-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="7c57d-104">Il codice seguente mostra <xref:System.Windows.Media.Media3D.DiffuseMaterial> e <xref:System.Windows.Media.Media3D.EmissiveMaterial> applicato in combinazione per aggiungere il blu all'aspetto del DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="7c57d-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="7c57d-105">Nel codice procedurale:</span><span class="sxs-lookup"><span data-stu-id="7c57d-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="7c57d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c57d-106">Example</span></span>  
 <span data-ttu-id="7c57d-107">Il codice seguente illustra l'intero esempio in XAML.</span><span class="sxs-lookup"><span data-stu-id="7c57d-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7c57d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c57d-108">Example</span></span>  
 <span data-ttu-id="7c57d-109">Di seguito è riportato l'intero esempio nel codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="7c57d-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7c57d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c57d-110">See also</span></span>

- [<span data-ttu-id="7c57d-111">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="7c57d-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="7c57d-112">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="7c57d-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="7c57d-113">Animare le proprietà Material in una scena 3D</span><span class="sxs-lookup"><span data-stu-id="7c57d-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="7c57d-114">Applicare un oggetto Material alle parti anteriore e posteriore di un oggetto 3D</span><span class="sxs-lookup"><span data-stu-id="7c57d-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
