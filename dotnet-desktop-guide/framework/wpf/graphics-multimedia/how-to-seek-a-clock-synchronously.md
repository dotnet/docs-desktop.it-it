---
title: 'Procedura: cercare un orologio in modalità sincrona'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963454"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="84dda-102">Procedura: cercare un orologio in modalità sincrona</span><span class="sxs-lookup"><span data-stu-id="84dda-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="84dda-103">Usare il <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodo per cercare un clock a un punto specifico in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="84dda-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="84dda-104">Nell'esempio seguente vengono illustrati <xref:System.Windows.Media.Animation.ClockController.Seek%2A> i <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> metodi e di un oggetto <xref:System.Windows.Media.Animation.ClockController> .</span><span class="sxs-lookup"><span data-stu-id="84dda-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="84dda-105">Questo esempio illustra come cercare un oggetto <xref:System.Windows.Media.Animation.Clock> . per un esempio che illustra come cercare uno storyboard, vedere [cercare uno storyboard in modo sincrono](how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="84dda-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="84dda-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="84dda-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
