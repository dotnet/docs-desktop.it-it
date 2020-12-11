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
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="0792b-102">Cenni preliminari sul componente Timer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="0792b-102">Timer Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0792b-103">Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="0792b-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="0792b-104">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0792b-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="0792b-105">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0792b-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="0792b-106">Proprietà, metodi ed eventi chiave</span><span class="sxs-lookup"><span data-stu-id="0792b-106">Key Properties, Methods, and Events</span></span>  

 <span data-ttu-id="0792b-107">La lunghezza degli intervalli è definita dalla <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0792b-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="0792b-108">Quando il componente è abilitato, l' <xref:System.Windows.Forms.Timer.Tick> evento viene generato ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="0792b-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="0792b-109">Qui è possibile aggiungere il codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="0792b-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="0792b-110">Per altre informazioni, vedere [procedura: eseguire routine a intervalli prestabiliti con il componente Timer Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="0792b-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="0792b-111">I metodi principali del <xref:System.Windows.Forms.Timer> componente sono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A> , che attivano e disattivano il timer.</span><span class="sxs-lookup"><span data-stu-id="0792b-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="0792b-112">Quando il timer viene disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="0792b-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0792b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0792b-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="0792b-114">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="0792b-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="0792b-115">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0792b-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
