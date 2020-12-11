---
title: Eventi per proprietà modificate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 939972713ad95e9302c436268f4a6288a659ca6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965854"
---
# <a name="property-changed-events"></a><span data-ttu-id="a403f-102">Eventi per proprietà modificate</span><span class="sxs-lookup"><span data-stu-id="a403f-102">Property-Changed Events</span></span>

<span data-ttu-id="a403f-103">Se si desidera che il controllo invii notifiche quando una proprietà denominata *PropertyName* viene modificata, definire un evento denominato *PropertyName* `Changed` e un metodo denominato `On` *PropertyName* `Changed` che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="a403f-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="a403f-104">La convenzione di denominazione in Windows Forms consiste nell'accodare la parola *modificata* al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a403f-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="a403f-105">Il tipo delegato di evento associato per gli eventi di modifica della proprietà è <xref:System.EventHandler> e il tipo di dati dell'evento è <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="a403f-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="a403f-106">La classe base <xref:System.Windows.Forms.Control> definisce molti eventi di modifica delle proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColorChanged> ,, <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> , <xref:System.Windows.Forms.Control.LocationChanged> e altri.</span><span class="sxs-lookup"><span data-stu-id="a403f-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="a403f-107">Per informazioni generali sugli eventi, vedere [eventi](/dotnet/standard/events/index) ed [eventi in controlli Windows Forms](events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a403f-107">For background information about events, see [Events](/dotnet/standard/events/index) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="a403f-108">Gli eventi di modifica delle proprietà sono utili perché consentono ai consumer di un controllo di alleghi gestori eventi che rispondono alla modifica.</span><span class="sxs-lookup"><span data-stu-id="a403f-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="a403f-109">Se il controllo deve rispondere a un evento di modifica della proprietà che genera, eseguire l'override del `On` metodo *PropertyName* corrispondente `Changed` invece di allegare un delegato all'evento.</span><span class="sxs-lookup"><span data-stu-id="a403f-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="a403f-110">Un controllo in genere risponde a un evento di modifica della proprietà aggiornando altre proprietà o ridisegnando parte o tutta la relativa superficie di disegno.</span><span class="sxs-lookup"><span data-stu-id="a403f-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="a403f-111">Nell'esempio seguente viene illustrato il modo in cui il `FlashTrackBar` controllo personalizzato risponde ad alcuni eventi di modifica della proprietà da cui eredita <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="a403f-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="a403f-112">Per l'esempio completo, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="a403f-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a403f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a403f-113">See also</span></span>

- [<span data-ttu-id="a403f-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="a403f-114">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="a403f-115">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a403f-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="a403f-116">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="a403f-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
