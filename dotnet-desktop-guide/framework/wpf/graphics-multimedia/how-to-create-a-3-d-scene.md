---
title: 'Procedura: creare una scena 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968029"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="fd3a9-102">Procedura: creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="fd3a9-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="fd3a9-103">Questo esempio illustra come creare un oggetto 3D simile a un foglio di carta Flat che è stato ruotato.</span><span class="sxs-lookup"><span data-stu-id="fd3a9-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="fd3a9-104"><xref:System.Windows.Controls.Viewport3D>Per creare questa semplice scena 3D, viene usato un insieme ai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd3a9-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="fd3a9-105">Viene creata una fotocamera usando un <xref:System.Windows.Media.Media3D.PerspectiveCamera> .</span><span class="sxs-lookup"><span data-stu-id="fd3a9-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="fd3a9-106">La fotocamera specifica quale parte della scena 3D è visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="fd3a9-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="fd3a9-107">Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> .</span><span class="sxs-lookup"><span data-stu-id="fd3a9-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="fd3a9-108">Viene specificato un materiale da visualizzare sulla superficie dell'oggetto (sfumatura lineare in questo esempio) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> .</span><span class="sxs-lookup"><span data-stu-id="fd3a9-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="fd3a9-109">Viene creata una luce per illuminare l'oggetto usando <xref:System.Windows.Media.Media3D.DirectionalLight> .</span><span class="sxs-lookup"><span data-stu-id="fd3a9-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd3a9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd3a9-110">Example</span></span>  
 <span data-ttu-id="fd3a9-111">Il codice seguente illustra come creare una scena 3D in XAML.</span><span class="sxs-lookup"><span data-stu-id="fd3a9-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="fd3a9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd3a9-112">Example</span></span>  
 <span data-ttu-id="fd3a9-113">Il codice seguente illustra come creare la stessa scena 3D nel codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="fd3a9-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fd3a9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd3a9-114">See also</span></span>

- [<span data-ttu-id="fd3a9-115">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="fd3a9-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
