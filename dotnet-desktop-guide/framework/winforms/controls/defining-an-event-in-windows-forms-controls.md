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
# <a name="defining-an-event-in-windows-forms-controls"></a>Definizione di un evento nei controlli Windows Form

Per informazioni dettagliate sulla definizione di eventi personalizzati, vedere [eventi](/dotnet/standard/events/index). Se si definisce un evento che non presenta dati associati, usare il tipo base per i dati dell'evento, <xref:System.EventArgs>, e usare <xref:System.EventHandler> come delegato dell'evento. Tutto ciò che rimane da fare è definire un membro evento e un metodo `On` *EventName* protetto che generi l'evento.  
  
 Il frammento di codice seguente illustra come il controllo personalizzato `FlashTrackBar` definisce un evento personalizzato, `ValueChanged`. Per il codice completo dell' `FlashTrackBar` esempio, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Eventi nei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Eventi](/dotnet/standard/events/index)
