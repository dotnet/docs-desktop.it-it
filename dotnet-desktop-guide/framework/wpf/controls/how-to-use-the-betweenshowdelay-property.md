---
title: 'Procedura: utilizzare la proprietà BetweenShowDelay'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964591"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="fbd23-102">Procedura: utilizzare la proprietà BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="fbd23-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="fbd23-103">In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà Time in modo che le descrizioni comandi vengano visualizzate rapidamente, con scarso o nessun ritardo, quando un utente sposta il puntatore del mouse da una descrizione comando direttamente a un'altra.</span><span class="sxs-lookup"><span data-stu-id="fbd23-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd23-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbd23-104">Example</span></span>  
 <span data-ttu-id="fbd23-105">Nell'esempio seguente la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> proprietà è impostata su un secondo (1000 millisecondi) e l'oggetto <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi i <xref:System.Windows.Shapes.Ellipse> controlli.</span><span class="sxs-lookup"><span data-stu-id="fbd23-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="fbd23-106">Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi si sposta il puntatore del mouse su un'altra ellisse entro due secondi e la si sospende, viene visualizzata immediatamente la descrizione comando della seconda ellisse.</span><span class="sxs-lookup"><span data-stu-id="fbd23-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="fbd23-107">In uno degli scenari seguenti, <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> si applica, che fa in modo che la descrizione comando per la seconda ellisse attenda un secondo prima che venga visualizzata:</span><span class="sxs-lookup"><span data-stu-id="fbd23-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="fbd23-108">Se il tempo necessario per spostarsi sul secondo pulsante è maggiore di due secondi.</span><span class="sxs-lookup"><span data-stu-id="fbd23-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="fbd23-109">Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.</span><span class="sxs-lookup"><span data-stu-id="fbd23-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="fbd23-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd23-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="fbd23-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="fbd23-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="fbd23-112">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="fbd23-112">ToolTip Overview</span></span>](tooltip-overview.md)
