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
# <a name="how-to-use-the-betweenshowdelay-property"></a>Procedura: utilizzare la proprietà BetweenShowDelay
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà Time in modo che le descrizioni comandi vengano visualizzate rapidamente, con scarso o nessun ritardo, quando un utente sposta il puntatore del mouse da una descrizione comando direttamente a un'altra.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> proprietà è impostata su un secondo (1000 millisecondi) e l'oggetto <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi i <xref:System.Windows.Shapes.Ellipse> controlli. Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi si sposta il puntatore del mouse su un'altra ellisse entro due secondi e la si sospende, viene visualizzata immediatamente la descrizione comando della seconda ellisse.  
  
 In uno degli scenari seguenti, <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> si applica, che fa in modo che la descrizione comando per la seconda ellisse attenda un secondo prima che venga visualizzata:  
  
- Se il tempo necessario per spostarsi sul secondo pulsante è maggiore di due secondi.  
  
- Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Procedure](tooltip-how-to-topics.md)
- [Panoramica sul controllo ToolTip](tooltip-overview.md)
