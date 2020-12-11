---
title: 'Procedura: creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968005"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="dc547-102">Procedura: creare una geometria combinata</span><span class="sxs-lookup"><span data-stu-id="dc547-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="dc547-103">Questo esempio illustra come combinare le geometrie.</span><span class="sxs-lookup"><span data-stu-id="dc547-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="dc547-104">Per combinare due geometrie, usare un <xref:System.Windows.Media.CombinedGeometry> oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc547-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="dc547-105">Impostare le <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> proprietà e con le due geometrie da combinare e impostare la <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà, che determina il modo in cui le geometrie verranno combinate insieme, a `Union` , `Intersect` , `Exclude` o `Xor` .</span><span class="sxs-lookup"><span data-stu-id="dc547-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="dc547-106">Per creare una geometria composta da due o più geometrie, usare un oggetto <xref:System.Windows.Media.GeometryGroup> .</span><span class="sxs-lookup"><span data-stu-id="dc547-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc547-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc547-107">Example</span></span>  
 <span data-ttu-id="dc547-108">Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria di `Exclude` .</span><span class="sxs-lookup"><span data-stu-id="dc547-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="dc547-109">Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="dc547-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="dc547-110">![Risultati della modalità di combinazione Exclude](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="dc547-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="dc547-111">Esclusione geometria combinata</span><span class="sxs-lookup"><span data-stu-id="dc547-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="dc547-112">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Intersect` .</span><span class="sxs-lookup"><span data-stu-id="dc547-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="dc547-113">Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="dc547-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="dc547-114">![Risultati della modalità di combinazione Intersect](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="dc547-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="dc547-115">Intersezione geometria combinata</span><span class="sxs-lookup"><span data-stu-id="dc547-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="dc547-116">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Union` .</span><span class="sxs-lookup"><span data-stu-id="dc547-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="dc547-117">Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="dc547-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="dc547-118">![Risultati della modalità di combinazione Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="dc547-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="dc547-119">Unione Geometry combinata</span><span class="sxs-lookup"><span data-stu-id="dc547-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="dc547-120">Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Xor` .</span><span class="sxs-lookup"><span data-stu-id="dc547-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="dc547-121">Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.</span><span class="sxs-lookup"><span data-stu-id="dc547-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="dc547-122">![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="dc547-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="dc547-123">XOR Geometry combinato</span><span class="sxs-lookup"><span data-stu-id="dc547-123">Combined Geometry Xor</span></span>
