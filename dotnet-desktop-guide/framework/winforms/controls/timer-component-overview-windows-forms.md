---
title: Panoramica del componente Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: ca1a7bf304da3fd602e3b0c36bb3aa20cd6b1345
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960922"
---
# <a name="timer-component-overview-windows-forms"></a>Cenni preliminari sul componente Timer (Windows Form)

Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari. Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Proprietà, metodi ed eventi chiave  

 La lunghezza degli intervalli è definita dalla <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è in millisecondi. Quando il componente è abilitato, l' <xref:System.Windows.Forms.Timer.Tick> evento viene generato ogni intervallo. Qui è possibile aggiungere il codice da eseguire. Per altre informazioni, vedere [procedura: eseguire routine a intervalli prestabiliti con il componente Timer Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md). I metodi principali del <xref:System.Windows.Forms.Timer> componente sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A> , che attivano e disattivano il timer. Quando il timer viene disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Limitazioni della proprietà Interval del componente Timer di Windows Form](limitations-of-the-timer-component-interval-property.md)
