---
title: Override del metodo OnPaint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 140c3e880300f8b1428dd23d946f25d095189fb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965023"
---
# <a name="overriding-the-onpaint-method"></a>Override del metodo OnPaint

I passaggi di base per eseguire l'override di qualsiasi evento definito nel .NET Framework sono identici e vengono riepilogati nell'elenco seguente.  
  
#### <a name="to-override-an-inherited-event"></a>Per eseguire l'override di un evento ereditato  
  
1. Eseguire l'override del `On` metodo *EventName* protetto.  
  
2. Chiamare il `On` metodo *EventName* della classe base dal metodo EventName sottoposto a override `On`  , in modo che i delegati registrati ricevano l'evento.  
  
 L' <xref:System.Windows.Forms.Control.Paint> evento viene descritto in dettaglio in questo articolo perché ogni controllo Windows Forms deve eseguire l'override dell' <xref:System.Windows.Forms.Control.Paint> evento da cui eredita <xref:System.Windows.Forms.Control> . La classe base non <xref:System.Windows.Forms.Control> sa come deve essere disegnato un controllo derivato e non fornisce alcuna logica di disegno nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di <xref:System.Windows.Forms.Control> Invia semplicemente l' <xref:System.Windows.Forms.Control.Paint> evento ai ricevitori di eventi registrati.  
  
 Se è stato usato l'esempio in [procedura: sviluppare un semplice controllo di Windows Forms](how-to-develop-a-simple-windows-forms-control.md), è stato illustrato un esempio di override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. Il frammento di codice seguente viene tratto da tale esempio.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 La <xref:System.Windows.Forms.PaintEventArgs> classe contiene i dati per l' <xref:System.Windows.Forms.Control.Paint> evento. Dispone di due proprietà, come illustrato nel codice seguente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> è il rettangolo da disegnare e la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà fa riferimento a un <xref:System.Drawing.Graphics> oggetto. Le classi nello <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi sono classi gestite che forniscono l'accesso alla funzionalità di GDI+, la nuova libreria grafica di Windows. L' <xref:System.Drawing.Graphics> oggetto dispone di metodi per creare punti, stringhe, linee, archi, ellissi e molte altre forme.  
  
 Un controllo richiama il <xref:System.Windows.Forms.Control.OnPaint%2A> Metodo ogni volta che è necessario modificare la visualizzazione. Questo metodo genera, a sua volta <xref:System.Windows.Forms.Control.Paint> , l'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](/dotnet/standard/events/index)
- [Rendering di un controllo Windows Form](rendering-a-windows-forms-control.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
