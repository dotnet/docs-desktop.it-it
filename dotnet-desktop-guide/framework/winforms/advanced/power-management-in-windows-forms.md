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
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="f4ac3-102">Risparmio energia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f4ac3-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="f4ac3-103">Le applicazioni Windows Forms possono sfruttare le funzionalità di risparmio energia del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="f4ac3-104">Le applicazioni possono monitorare lo stato di alimentazione di un computer e intervenire quando si verifica una modifica dello stato.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="f4ac3-105">Se, ad esempio, l'applicazione è in esecuzione in un computer portatile, potrebbe essere necessario disabilitare determinate funzionalità nell'applicazione quando il costo della batteria del computer rientra in un determinato livello.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="f4ac3-106">Il .NET Framework fornisce un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento che si verifica ogni volta che viene apportata una modifica allo stato di alimentazione, ad esempio quando un utente sospende o riprende il sistema operativo oppure quando lo stato dell'alimentazione CA o lo stato della batteria cambia.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="f4ac3-107">La <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà della <xref:System.Windows.Forms.SystemInformation> classe può essere utilizzata per eseguire una query per lo stato corrente, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="f4ac3-108">Oltre alle <xref:System.Windows.Forms.BatteryChargeStatus> enumerazioni, la <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> proprietà contiene anche enumerazioni per determinare la capacità della batteria ( <xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A> ) e la percentuale di carica della batteria ( <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> , <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> ).</span><span class="sxs-lookup"><span data-stu-id="f4ac3-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="f4ac3-109">È possibile utilizzare il <xref:System.Windows.Forms.Application.SetSuspendState%2A> metodo di <xref:System.Windows.Forms.Application> per attivare la modalità di sospensione o sospensione del computer.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="f4ac3-110">Se l' `force` argomento è impostato su `false` , il sistema operativo trasmette un evento a tutte le applicazioni che richiedono le autorizzazioni di sospensione.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="f4ac3-111">Se l' `disableWakeEvent` argomento è impostato su `true` , il sistema operativo Disabilita tutti gli eventi di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="f4ac3-112">Nell'esempio di codice riportato di seguito viene illustrato come attivare la modalità di ibernazione di un computer.</span><span class="sxs-lookup"><span data-stu-id="f4ac3-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f4ac3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4ac3-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
