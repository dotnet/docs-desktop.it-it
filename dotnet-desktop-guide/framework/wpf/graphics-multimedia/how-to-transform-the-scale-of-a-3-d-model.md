---
title: 'Procedura: trasformare la scala di un modello 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965557"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="1d8b9-102">Procedura: trasformare la scala di un modello 3D</span><span class="sxs-lookup"><span data-stu-id="1d8b9-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="1d8b9-103">Questo esempio illustra come ridimensionare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="1d8b9-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="1d8b9-104">Per ridimensionare un oggetto 3D, usare <xref:System.Windows.Media.Media3D.ScaleTransform3D> .</span><span class="sxs-lookup"><span data-stu-id="1d8b9-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="1d8b9-105">Le <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> proprietà, e <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> ridimensionano l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="1d8b9-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="1d8b9-106">Ad esempio, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valore di 1,5 estende un oggetto a 150% della larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="1d8b9-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="1d8b9-107"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>Il valore 0,5 compatta l'altezza di un oggetto del 50%.</span><span class="sxs-lookup"><span data-stu-id="1d8b9-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="1d8b9-108">Il codice seguente illustra l'uso di <xref:System.Windows.Media.Media3D.ScaleTransform3D> come trasformazione per un oggetto <xref:System.Windows.Media.Media3D.GeometryModel3D> .</span><span class="sxs-lookup"><span data-stu-id="1d8b9-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="1d8b9-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d8b9-109">Example</span></span>  
 <span data-ttu-id="1d8b9-110">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="1d8b9-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1d8b9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8b9-111">See also</span></span>

- [<span data-ttu-id="1d8b9-112">Animare le conversioni 3D</span><span class="sxs-lookup"><span data-stu-id="1d8b9-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="1d8b9-113">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="1d8b9-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="1d8b9-114">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="1d8b9-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
