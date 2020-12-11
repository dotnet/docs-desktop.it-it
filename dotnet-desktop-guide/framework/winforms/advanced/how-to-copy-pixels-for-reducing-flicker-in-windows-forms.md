---
title: 'Procedura: copiare i pixel per ridurre lo sfarfallio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952410"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="71f5d-102">Procedura: Copiare i pixel per ridurre lo sfarfallio nei Windows Form</span><span class="sxs-lookup"><span data-stu-id="71f5d-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="71f5d-103">Quando si aggiunge un'animazione a un grafico semplice, gli utenti possono talvolta riscontrare sfarfallio o altri effetti visivi indesiderati.</span><span class="sxs-lookup"><span data-stu-id="71f5d-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="71f5d-104">Un modo per limitare questo problema consiste nell'usare un processo "BitBlt" sul grafico.</span><span class="sxs-lookup"><span data-stu-id="71f5d-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="71f5d-105">BitBlt è il "trasferimento a blocchi di bit" dei dati relativi ai colori da un rettangolo di origine di pixel a un rettangolo di destinazione di pixel.</span><span class="sxs-lookup"><span data-stu-id="71f5d-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="71f5d-106">Con Windows Forms, BitBlt viene eseguita utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="71f5d-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="71f5d-107">Nei parametri del metodo si specificano l'origine e la destinazione (come punti), le dimensioni dell'area da copiare e l'oggetto Graphics utilizzato per disegnare la nuova forma.</span><span class="sxs-lookup"><span data-stu-id="71f5d-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="71f5d-108">Nell'esempio seguente viene disegnata una forma sul form nel <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="71f5d-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="71f5d-109"><xref:System.Drawing.Graphics.CopyFromScreen%2A>Viene quindi utilizzato il metodo per duplicare la forma.</span><span class="sxs-lookup"><span data-stu-id="71f5d-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71f5d-110">Se si imposta la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà del form su, `true` il codice basato su grafica nell'evento verrà sottoposta a <xref:System.Windows.Forms.Control.Paint> doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="71f5d-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="71f5d-111">Sebbene non sia possibile ottenere miglioramenti in termini di prestazioni quando si usa il codice riportato di seguito, è opportuno tenere presente quando si lavora con codice di manipolazione grafica più complesso.</span><span class="sxs-lookup"><span data-stu-id="71f5d-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71f5d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="71f5d-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71f5d-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="71f5d-113">Compiling the Code</span></span>  
 <span data-ttu-id="71f5d-114">Il codice precedente viene eseguito nel gestore eventi del form in <xref:System.Windows.Forms.Control.Paint> modo che la grafica venga mantenute quando il modulo viene ridisegnato.</span><span class="sxs-lookup"><span data-stu-id="71f5d-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="71f5d-115">Di conseguenza, non chiamare metodi correlati alla grafica nel <xref:System.Windows.Forms.Form.Load> gestore eventi, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.</span><span class="sxs-lookup"><span data-stu-id="71f5d-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f5d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71f5d-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="71f5d-117">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="71f5d-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="71f5d-118">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="71f5d-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
