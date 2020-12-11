---
title: Limitazioni della proprietà intervallo componente timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 90023a20b32cc4f5709d35f4e8c0a339e1d46751
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965095"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Limitazioni della proprietà Interval del componente Timer di Windows Form

Il <xref:System.Windows.Forms.Timer> componente Windows Forms dispone di una <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che passano tra un evento del timer e il successivo. A meno che il componente non sia disabilitato, un timer continua a ricevere l' <xref:System.Windows.Forms.Timer.Tick> evento a intervalli di tempo approssimativamente uguali.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>Proprietà Interval  

 La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da considerare durante la programmazione di un <xref:System.Windows.Forms.Timer> componente:  
  
- Se l'applicazione o un'altra applicazione sta effettuando richieste elevate al sistema, ad esempio cicli lunghi, calcoli intensivi o accesso di unità, rete o porta, è possibile che l'applicazione non ottenga gli eventi del timer con la stessa frequenza con cui viene <xref:System.Windows.Forms.Timer.Interval%2A> specificata la proprietà.  
  
- Non è garantito che l'intervallo venga trascorso esattamente nel tempo. Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché provare a tenere traccia del tempo accumulato internamente.  
  
- La precisione della <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è in millisecondi. Alcuni computer forniscono un contatore ad alta risoluzione con una risoluzione superiore a millisecondi. La disponibilità di tale contatore dipende dall'hardware del processore del computer.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Panoramica del componente Timer](timer-component-overview-windows-forms.md)
