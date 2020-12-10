---
title: 'Procedura: modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951002"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="781d5-102">Procedura: modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="781d5-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="781d5-103">La <xref:System.Windows.Media.Animation.ClockController> proprietà di un oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> consente di modificare la velocità di un oggetto <xref:System.Windows.Media.Animation.Clock> senza modificare il valore <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> dell'oggetto dell'orologio <xref:System.Windows.Media.Animation.Timeline> .</span><span class="sxs-lookup"><span data-stu-id="781d5-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="781d5-104">Nell'esempio seguente <xref:System.Windows.Media.Animation.ClockController> viene usato un oggetto per modificare in modo interattivo l'oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> di un orologio.</span><span class="sxs-lookup"><span data-stu-id="781d5-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="781d5-105">L' <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> evento e la proprietà Clock <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> vengono usati per visualizzare la velocità globale corrente del clock ogni volta che viene modificata la relativa Interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> .</span><span class="sxs-lookup"><span data-stu-id="781d5-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="781d5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="781d5-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
