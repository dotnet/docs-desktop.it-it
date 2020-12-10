---
title: Definire un evento nei controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: fabffc02ecf921eed428ec1ec452aa60c77b5987
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951022"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="fd3d1-102">Definizione di un evento nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="fd3d1-102">Defining an Event in Windows Forms Controls</span></span>

<span data-ttu-id="fd3d1-103">Per informazioni dettagliate sulla definizione di eventi personalizzati, vedere [eventi](/dotnet/standard/events/index).</span><span class="sxs-lookup"><span data-stu-id="fd3d1-103">For details about defining custom events, see [Events](/dotnet/standard/events/index).</span></span> <span data-ttu-id="fd3d1-104">Se si definisce un evento che non presenta dati associati, usare il tipo base per i dati dell'evento, <xref:System.EventArgs>, e usare <xref:System.EventHandler> come delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fd3d1-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="fd3d1-105">Tutto ciò che rimane da fare è definire un membro evento e un metodo `On` *EventName* protetto che generi l'evento.</span><span class="sxs-lookup"><span data-stu-id="fd3d1-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="fd3d1-106">Il frammento di codice seguente illustra come il controllo personalizzato `FlashTrackBar` definisce un evento personalizzato, `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="fd3d1-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="fd3d1-107">Per il codice completo dell' `FlashTrackBar` esempio, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="fd3d1-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd3d1-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd3d1-108">See also</span></span>

- [<span data-ttu-id="fd3d1-109">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="fd3d1-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="fd3d1-110">Eventi</span><span class="sxs-lookup"><span data-stu-id="fd3d1-110">Events</span></span>](/dotnet/standard/events/index)
