---
title: Eventi nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 27edaf2d895453d64d35ba6eff724df583a9b7dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962194"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="3014f-102">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3014f-102">Events in Windows Forms Controls</span></span>

<span data-ttu-id="3014f-103">Un controllo Windows Forms eredita più di 60 eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3014f-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3014f-104">Che includono l' <xref:System.Windows.Forms.Control.Paint> evento, che determina la visualizzazione di un controllo, gli eventi correlati alla visualizzazione di una finestra, ad esempio gli eventi <xref:System.Windows.Forms.Control.Resize> e e <xref:System.Windows.Forms.Control.Layout> gli eventi di mouse e tastiera di basso livello.</span><span class="sxs-lookup"><span data-stu-id="3014f-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="3014f-105">Alcuni eventi di basso livello vengono sintetizzati <xref:System.Windows.Forms.Control> in eventi semantici, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="3014f-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="3014f-106">Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="3014f-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="3014f-107">Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato.</span><span class="sxs-lookup"><span data-stu-id="3014f-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="3014f-108">Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="3014f-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3014f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3014f-109">See also</span></span>

- [<span data-ttu-id="3014f-110">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="3014f-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="3014f-111">Gestione dell'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="3014f-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="3014f-112">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="3014f-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="3014f-113">Eventi</span><span class="sxs-lookup"><span data-stu-id="3014f-113">Events</span></span>](/dotnet/standard/events/index)
