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
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Procedura: modificare la velocità di un orologio senza cambiare la velocità della relativa sequenza temporale
La <xref:System.Windows.Media.Animation.ClockController> proprietà di un oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> consente di modificare la velocità di un oggetto <xref:System.Windows.Media.Animation.Clock> senza modificare il valore <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> dell'oggetto dell'orologio <xref:System.Windows.Media.Animation.Timeline> . Nell'esempio seguente <xref:System.Windows.Media.Animation.ClockController> viene usato un oggetto per modificare in modo interattivo l'oggetto <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> di un orologio. L' <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> evento e la proprietà Clock <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> vengono usati per visualizzare la velocità globale corrente del clock ogni volta che viene modificata la relativa Interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> .  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
