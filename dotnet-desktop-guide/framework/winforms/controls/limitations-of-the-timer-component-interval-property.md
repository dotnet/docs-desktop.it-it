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
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="0b69f-102">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b69f-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>

<span data-ttu-id="0b69f-103">Il <xref:System.Windows.Forms.Timer> componente Windows Forms dispone di una <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che passano tra un evento del timer e il successivo.</span><span class="sxs-lookup"><span data-stu-id="0b69f-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="0b69f-104">A meno che il componente non sia disabilitato, un timer continua a ricevere l' <xref:System.Windows.Forms.Timer.Tick> evento a intervalli di tempo approssimativamente uguali.</span><span class="sxs-lookup"><span data-stu-id="0b69f-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="0b69f-105">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0b69f-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="0b69f-106">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0b69f-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="0b69f-107">Proprietà Interval</span><span class="sxs-lookup"><span data-stu-id="0b69f-107">The Interval Property</span></span>  

 <span data-ttu-id="0b69f-108">La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da considerare durante la programmazione di un <xref:System.Windows.Forms.Timer> componente:</span><span class="sxs-lookup"><span data-stu-id="0b69f-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="0b69f-109">Se l'applicazione o un'altra applicazione sta effettuando richieste elevate al sistema, ad esempio cicli lunghi, calcoli intensivi o accesso di unità, rete o porta, è possibile che l'applicazione non ottenga gli eventi del timer con la stessa frequenza con cui viene <xref:System.Windows.Forms.Timer.Interval%2A> specificata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="0b69f-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="0b69f-110">Non è garantito che l'intervallo venga trascorso esattamente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0b69f-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="0b69f-111">Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché provare a tenere traccia del tempo accumulato internamente.</span><span class="sxs-lookup"><span data-stu-id="0b69f-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="0b69f-112">La precisione della <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0b69f-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="0b69f-113">Alcuni computer forniscono un contatore ad alta risoluzione con una risoluzione superiore a millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0b69f-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="0b69f-114">La disponibilità di tale contatore dipende dall'hardware del processore del computer.</span><span class="sxs-lookup"><span data-stu-id="0b69f-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b69f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b69f-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="0b69f-116">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="0b69f-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="0b69f-117">Panoramica del componente Timer</span><span class="sxs-lookup"><span data-stu-id="0b69f-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
