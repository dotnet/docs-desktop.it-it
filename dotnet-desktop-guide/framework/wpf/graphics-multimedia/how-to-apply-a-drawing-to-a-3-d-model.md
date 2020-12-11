---
title: 'Procedura: applicare un disegno a un modello 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 794ca9a48bcec42c3eee4d8da143f3ae9d27fcf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966895"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="486f8-102">Procedura: applicare un disegno a un modello 3D</span><span class="sxs-lookup"><span data-stu-id="486f8-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="486f8-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingBrush> come <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.</span><span class="sxs-lookup"><span data-stu-id="486f8-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="486f8-104">Il codice seguente definisce un oggetto <xref:System.Windows.Media.DrawingGroup> come contenuto di un oggetto <xref:System.Windows.Media.DrawingBrush> .</span><span class="sxs-lookup"><span data-stu-id="486f8-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="486f8-105"><xref:System.Windows.Media.DrawingBrush>Viene impostato come la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un piano 3D.</span><span class="sxs-lookup"><span data-stu-id="486f8-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="486f8-106">Spesso è consigliabile definire oggetti e valori complessi come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="486f8-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="486f8-107">Per ulteriori informazioni, vedere [risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) .</span><span class="sxs-lookup"><span data-stu-id="486f8-107">See [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="486f8-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="486f8-108">Example</span></span>

<span data-ttu-id="486f8-109">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="486f8-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="486f8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="486f8-110">See also</span></span>

- [<span data-ttu-id="486f8-111">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="486f8-111">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="486f8-112">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="486f8-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="486f8-113">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="486f8-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="486f8-114">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="486f8-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
