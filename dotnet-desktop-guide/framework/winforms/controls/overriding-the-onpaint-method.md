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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="ad044-102">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="ad044-102">Overriding the OnPaint Method</span></span>

<span data-ttu-id="ad044-103">I passaggi di base per eseguire l'override di qualsiasi evento definito nel .NET Framework sono identici e vengono riepilogati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="ad044-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="ad044-104">Per eseguire l'override di un evento ereditato</span><span class="sxs-lookup"><span data-stu-id="ad044-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="ad044-105">Eseguire l'override del `On` metodo *EventName* protetto.</span><span class="sxs-lookup"><span data-stu-id="ad044-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="ad044-106">Chiamare il `On` metodo *EventName* della classe base dal metodo EventName sottoposto a override `On`  , in modo che i delegati registrati ricevano l'evento.</span><span class="sxs-lookup"><span data-stu-id="ad044-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="ad044-107">L' <xref:System.Windows.Forms.Control.Paint> evento viene descritto in dettaglio in questo articolo perché ogni controllo Windows Forms deve eseguire l'override dell' <xref:System.Windows.Forms.Control.Paint> evento da cui eredita <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="ad044-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ad044-108">La classe base non <xref:System.Windows.Forms.Control> sa come deve essere disegnato un controllo derivato e non fornisce alcuna logica di disegno nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ad044-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ad044-109">Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di <xref:System.Windows.Forms.Control> Invia semplicemente l' <xref:System.Windows.Forms.Control.Paint> evento ai ricevitori di eventi registrati.</span><span class="sxs-lookup"><span data-stu-id="ad044-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="ad044-110">Se è stato usato l'esempio in [procedura: sviluppare un semplice controllo di Windows Forms](how-to-develop-a-simple-windows-forms-control.md), è stato illustrato un esempio di override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ad044-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ad044-111">Il frammento di codice seguente viene tratto da tale esempio.</span><span class="sxs-lookup"><span data-stu-id="ad044-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="ad044-112">La <xref:System.Windows.Forms.PaintEventArgs> classe contiene i dati per l' <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="ad044-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="ad044-113">Dispone di due proprietà, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ad044-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="ad044-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> è il rettangolo da disegnare e la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà fa riferimento a un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad044-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="ad044-115">Le classi nello <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi sono classi gestite che forniscono l'accesso alla funzionalità di GDI+, la nuova libreria grafica di Windows.</span><span class="sxs-lookup"><span data-stu-id="ad044-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="ad044-116">L' <xref:System.Drawing.Graphics> oggetto dispone di metodi per creare punti, stringhe, linee, archi, ellissi e molte altre forme.</span><span class="sxs-lookup"><span data-stu-id="ad044-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="ad044-117">Un controllo richiama il <xref:System.Windows.Forms.Control.OnPaint%2A> Metodo ogni volta che è necessario modificare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad044-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="ad044-118">Questo metodo genera, a sua volta <xref:System.Windows.Forms.Control.Paint> , l'evento.</span><span class="sxs-lookup"><span data-stu-id="ad044-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad044-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad044-119">See also</span></span>

- [<span data-ttu-id="ad044-120">Eventi</span><span class="sxs-lookup"><span data-stu-id="ad044-120">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="ad044-121">Rendering di un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad044-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="ad044-122">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="ad044-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
