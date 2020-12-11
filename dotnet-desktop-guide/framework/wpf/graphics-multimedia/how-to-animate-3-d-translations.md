---
title: 'Procedura: animare le traduzioni 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960859"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="6b5cd-102">Procedura: animare le traduzioni 3D</span><span class="sxs-lookup"><span data-stu-id="6b5cd-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="6b5cd-103">In questo argomento viene illustrato come aggiungere un'animazione a una trasformazione di conversione impostata su un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="6b5cd-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="6b5cd-104">Il codice seguente illustra l'applicazione di un <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto alla <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà di un oggetto <xref:System.Windows.Media.Media3D.GeometryModel3D> .</span><span class="sxs-lookup"><span data-stu-id="6b5cd-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="6b5cd-105">La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà di questo <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto viene animata usando il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6b5cd-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="6b5cd-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b5cd-106">Example</span></span>  
 <span data-ttu-id="6b5cd-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="6b5cd-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6b5cd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b5cd-108">See also</span></span>

- [<span data-ttu-id="6b5cd-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="6b5cd-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6b5cd-110">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="6b5cd-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="6b5cd-111">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="6b5cd-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="6b5cd-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="6b5cd-112">Transforms Overview</span></span>](transforms-overview.md)
