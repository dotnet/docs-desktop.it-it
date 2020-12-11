---
title: Risparmio energia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963109"
---
# <a name="power-management-in-windows-forms"></a>Risparmio energia in Windows Form
Le applicazioni Windows Forms possono sfruttare le funzionalità di risparmio energia del sistema operativo Windows. Le applicazioni possono monitorare lo stato di alimentazione di un computer e intervenire quando si verifica una modifica dello stato. Se, ad esempio, l'applicazione è in esecuzione in un computer portatile, potrebbe essere necessario disabilitare determinate funzionalità nell'applicazione quando il costo della batteria del computer rientra in un determinato livello.  
  
 Il .NET Framework fornisce un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento che si verifica ogni volta che viene apportata una modifica allo stato di alimentazione, ad esempio quando un utente sospende o riprende il sistema operativo oppure quando lo stato dell'alimentazione CA o lo stato della batteria cambia. La <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà della <xref:System.Windows.Forms.SystemInformation> classe può essere utilizzata per eseguire una query per lo stato corrente, come illustrato nell'esempio di codice seguente.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Oltre alle <xref:System.Windows.Forms.BatteryChargeStatus> enumerazioni, la <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà contiene anche enumerazioni per determinare la capacità della batteria ( <xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A> ) e la percentuale di carica della batteria ( <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> , <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> ).  
  
 È possibile utilizzare il <xref:System.Windows.Forms.Application.SetSuspendState%2A> metodo di <xref:System.Windows.Forms.Application> per attivare la modalità di sospensione o sospensione del computer. Se l' `force` argomento è impostato su `false` , il sistema operativo trasmette un evento a tutte le applicazioni che richiedono le autorizzazioni di sospensione. Se l' `disableWakeEvent` argomento è impostato su `true` , il sistema operativo Disabilita tutti gli eventi di riattivazione.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come attivare la modalità di ibernazione di un computer.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
