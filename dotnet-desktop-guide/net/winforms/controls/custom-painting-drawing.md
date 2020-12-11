---
title: Disegno personalizzato per un controllo
description: Informazioni su come personalizzare l'aspetto di un controllo tramite il metodo OnPaint e l'evento Paint in Windows Forms per .NET.
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
f1_keywords:
- OnPaint
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 8d9775c02addb68cc962cdc2e4bf2d1baa6ab2a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967327"
---
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a><span data-ttu-id="c813f-103">Disegno e disegno sui controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="c813f-103">Painting and drawing on controls (Windows Forms .NET)</span></span>

<span data-ttu-id="c813f-104">Il disegno personalizzato dei controlli è una delle numerose attività complesse semplificate dal Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c813f-104">Custom painting of controls is one of the many complicated tasks made easy by Windows Forms.</span></span> <span data-ttu-id="c813f-105">Quando si crea un controllo personalizzato, sono disponibili molte opzioni per gestire l'aspetto grafico del controllo.</span><span class="sxs-lookup"><span data-stu-id="c813f-105">When authoring a custom control, you have many options available to handle your control's graphical appearance.</span></span> <span data-ttu-id="c813f-106">Se si sta creando un [controllo personalizzato](custom.md#custom-controls), ovvero un controllo che eredita da <xref:System.Windows.Forms.Control> , è necessario fornire il codice per eseguire il rendering della relativa rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="c813f-106">If you're authoring a [custom control](custom.md#custom-controls), that is, a control that inherits from <xref:System.Windows.Forms.Control>, you must provide code to render its graphical representation.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="c813f-107">Se si sta creando un [controllo composito](custom.md#composite-controls), ovvero un controllo che eredita da <xref:System.Windows.Forms.UserControl> o uno dei controlli Windows Forms esistenti, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice grafico.</span><span class="sxs-lookup"><span data-stu-id="c813f-107">If you're creating a [composite control](custom.md#composite-controls), that is a control that inherits from <xref:System.Windows.Forms.UserControl> or one of the existing Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span>

<span data-ttu-id="c813f-108">Se si desidera fornire il rendering personalizzato per un controllo esistente senza creare un nuovo controllo, le opzioni diventano più limitate.</span><span class="sxs-lookup"><span data-stu-id="c813f-108">If you want to provide custom rendering for an existing control without creating a new control, your options become more limited.</span></span> <span data-ttu-id="c813f-109">Tuttavia, esiste ancora un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c813f-109">However, there are still a wide range of graphical possibilities for your controls and applications.</span></span>

<span data-ttu-id="c813f-110">Per il rendering del controllo sono necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c813f-110">The following elements are involved in control rendering:</span></span>

- <span data-ttu-id="c813f-111">Funzionalità di disegno fornita dalla classe base <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c813f-111">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="c813f-112">Elementi essenziali della libreria grafica GDI.</span><span class="sxs-lookup"><span data-stu-id="c813f-112">The essential elements of the GDI graphics library.</span></span>
- <span data-ttu-id="c813f-113">Geometria dell'area di disegno.</span><span class="sxs-lookup"><span data-stu-id="c813f-113">The geometry of the drawing region.</span></span>
- <span data-ttu-id="c813f-114">Procedura per liberare risorse grafiche.</span><span class="sxs-lookup"><span data-stu-id="c813f-114">The procedure for freeing graphics resources.</span></span>

## <a name="drawing-provided-by-control"></a><span data-ttu-id="c813f-115">Disegno fornito dal controllo</span><span class="sxs-lookup"><span data-stu-id="c813f-115">Drawing provided by control</span></span>

<span data-ttu-id="c813f-116">La classe base <xref:System.Windows.Forms.Control> fornisce la funzionalità di disegno tramite il relativo <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="c813f-116">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c813f-117">Un controllo genera l' <xref:System.Windows.Forms.Control.Paint> evento ogni volta che è necessario aggiornare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c813f-117">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="c813f-118">Per ulteriori informazioni sugli eventi in .NET, vedere [gestione e generazione di eventi](/dotnet/standard/events/index).</span><span class="sxs-lookup"><span data-stu-id="c813f-118">For more information about events in the .NET, see [Handling and raising events](/dotnet/standard/events/index).</span></span>

<span data-ttu-id="c813f-119">La classe di dati dell'evento per l' <xref:System.Windows.Forms.Control.Paint> evento, <xref:System.Windows.Forms.PaintEventArgs> , include i dati necessari per il disegno di un handle di controllo in un oggetto Graphics e di un rettangolo che rappresenta l'area in cui disegnare.</span><span class="sxs-lookup"><span data-stu-id="c813f-119">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control - a handle to a graphics object and a rectangle that represents the region to draw in.</span></span>

```csharp
public class PaintEventArgs : EventArgs, IDisposable
{

    public System.Drawing.Rectangle ClipRectangle {get;}
    public System.Drawing.Graphics Graphics {get;}

    // Other properties and methods.
}
```

```vb
Public Class PaintEventArgs
    Inherits EventArgs
    Implements IDisposable

    Public ReadOnly Property ClipRectangle As System.Drawing.Rectangle
    Public ReadOnly Property Graphics As System.Drawing.Graphics

    ' Other properties and methods.
End Class
```

<span data-ttu-id="c813f-120"><xref:System.Drawing.Graphics> è una classe gestita che incapsula la funzionalità di disegno, come descritto nella discussione di GDI più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c813f-120"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this article.</span></span> <span data-ttu-id="c813f-121"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>È un'istanza della <xref:System.Drawing.Rectangle> struttura e definisce l'area disponibile in cui un controllo può essere disegnato.</span><span class="sxs-lookup"><span data-stu-id="c813f-121">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="c813f-122">Uno sviluppatore di controlli può calcolare <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> usando la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di geometria più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c813f-122">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this article.</span></span>

### <a name="onpaint"></a><span data-ttu-id="c813f-123">OnPaint</span><span class="sxs-lookup"><span data-stu-id="c813f-123">OnPaint</span></span>

<span data-ttu-id="c813f-124">Un controllo deve fornire la logica di rendering eseguendo l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo da cui eredita <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="c813f-124">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="c813f-125"><xref:System.Windows.Forms.Control.OnPaint%2A> Ottiene l'accesso a un oggetto Graphics e a un rettangolo da creare tramite l'oggetto <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> e le <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà dell' <xref:System.Windows.Forms.PaintEventArgs> istanza passata.</span><span class="sxs-lookup"><span data-stu-id="c813f-125"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>

<span data-ttu-id="c813f-126">Il codice seguente usa lo `System.Drawing` spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="c813f-126">The following code uses the `System.Drawing` namespace:</span></span>

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

<span data-ttu-id="c813f-127">Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base <xref:System.Windows.Forms.Control> non implementa alcuna funzionalità di disegno, ma richiama solo i delegati dell'evento registrati con l' <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="c813f-127">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class doesn't implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c813f-128">Quando si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> di, è in genere necessario richiamare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe base in modo che i delegati registrati ricevano l' <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="c813f-128">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c813f-129">Tuttavia, i controlli che disegnano l'intera superficie non devono richiamare l'oggetto della classe di base <xref:System.Windows.Forms.Control.OnPaint%2A> , in quanto introduce lo sfarfallio.</span><span class="sxs-lookup"><span data-stu-id="c813f-129">However, controls that paint their entire surface shouldn't invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span>

> [!NOTE]
> <span data-ttu-id="c813f-130">Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo; richiamare invece il <xref:System.Windows.Forms.Control.Invalidate%2A> Metodo (Ereditato da <xref:System.Windows.Forms.Control> ) o un altro metodo che richiama <xref:System.Windows.Forms.Control.Invalidate%2A> .</span><span class="sxs-lookup"><span data-stu-id="c813f-130">Don't invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="c813f-131">Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo richiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A> .</span><span class="sxs-lookup"><span data-stu-id="c813f-131">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="c813f-132">Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo è sottoposto a overload e, a seconda degli argomenti forniti a <xref:System.Windows.Forms.Control.Invalidate%2A> `e` , ridisegnato una parte o tutta la relativa area dello schermo.</span><span class="sxs-lookup"><span data-stu-id="c813f-132">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, redraws either some or all of its screen area.</span></span>

<span data-ttu-id="c813f-133">Il codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo verrà eseguito quando il controllo viene creato per la prima volta e ogni volta che viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c813f-133">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="c813f-134">Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:</span><span class="sxs-lookup"><span data-stu-id="c813f-134">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a><span data-ttu-id="c813f-135">OnPaintBackground</span><span class="sxs-lookup"><span data-stu-id="c813f-135">OnPaintBackground</span></span>

<span data-ttu-id="c813f-136">La <xref:System.Windows.Forms.Control> classe base definisce un altro metodo utile per il disegno, il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c813f-136">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing, the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<span data-ttu-id="c813f-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> Disegna lo sfondo (e, in questo modo, la forma) della finestra ed è garantito che sia veloce, mentre <xref:System.Windows.Forms.Control.OnPaint%2A> dipinge i dettagli e potrebbe essere più lento perché le singole richieste di disegno vengono combinate in un unico <xref:System.Windows.Forms.Control.Paint> evento che copre tutte le aree che devono essere ridisegnate.</span><span class="sxs-lookup"><span data-stu-id="c813f-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and in that way, the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="c813f-138">Potrebbe essere necessario richiamare l'oggetto <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si desidera creare uno sfondo sfumato per il controllo.</span><span class="sxs-lookup"><span data-stu-id="c813f-138">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>

<span data-ttu-id="c813f-139">Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ha una nomenclatura simile a un evento e accetta lo stesso argomento del `OnPaint` metodo, `OnPaintBackground` non è un vero metodo di evento.</span><span class="sxs-lookup"><span data-stu-id="c813f-139">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, `OnPaintBackground` is not a true event method.</span></span> <span data-ttu-id="c813f-140">Non è presente alcun `PaintBackground` evento e `OnPaintBackground` non richiama i delegati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c813f-140">There is no `PaintBackground` event and `OnPaintBackground` doesn't invoke event delegates.</span></span> <span data-ttu-id="c813f-141">Quando si esegue l'override del `OnPaintBackground` metodo, non è necessaria una classe derivata per richiamare il `OnPaintBackground` metodo della relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="c813f-141">When overriding the `OnPaintBackground` method, a derived class is not required to invoke the `OnPaintBackground` method of its base class.</span></span>

## <a name="gdi-basics"></a><span data-ttu-id="c813f-142">Nozioni fondamentali su GDI+</span><span class="sxs-lookup"><span data-stu-id="c813f-142">GDI+ Basics</span></span>

<span data-ttu-id="c813f-143">La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare diverse forme, ad esempio cerchi, triangoli, archi ed ellissi e metodi per la visualizzazione di testo.</span><span class="sxs-lookup"><span data-stu-id="c813f-143">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, and methods for displaying text.</span></span> <span data-ttu-id="c813f-144">Lo <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi contiene gli spazi dei nomi e le classi che incapsulano elementi grafici come forme (cerchi, rettangoli, archi e altri), colori, tipi di carattere, pennelli e così via.</span><span class="sxs-lookup"><span data-stu-id="c813f-144">The <xref:System.Drawing?displayProperty=nameWithType> namespace contains namespaces and classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span><!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="c813f-145">Geometria dell'area di disegno</span><span class="sxs-lookup"><span data-stu-id="c813f-145">Geometry of the Drawing Region</span></span>

<span data-ttu-id="c813f-146">La <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo specifica l'area rettangolare disponibile per il controllo sullo schermo dell'utente, mentre la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> specifica l'area disegnata.</span><span class="sxs-lookup"><span data-stu-id="c813f-146">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is painted.</span></span> <span data-ttu-id="c813f-147">Un controllo potrebbe dover disegnare solo una parte dell'area disponibile, come nel caso in cui una piccola sezione della visualizzazione del controllo cambia.</span><span class="sxs-lookup"><span data-stu-id="c813f-147">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="c813f-148">In questi casi, uno sviluppatore di controlli deve calcolare il rettangolo effettivo da creare e passarlo a <xref:System.Windows.Forms.Control.Invalidate%2A> .</span><span class="sxs-lookup"><span data-stu-id="c813f-148">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="c813f-149">Le versioni di overload di <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un oggetto <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento usano tale argomento per generare la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="c813f-149">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>

## <a name="freeing-graphics-resources"></a><span data-ttu-id="c813f-150">Liberare risorse grafiche</span><span class="sxs-lookup"><span data-stu-id="c813f-150">Freeing Graphics Resources</span></span>

<span data-ttu-id="c813f-151">Gli oggetti grafici sono costosi perché usano risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="c813f-151">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="c813f-152">Tali oggetti includono le istanze della <xref:System.Drawing.Graphics?displayProperty=nameWithType> classe e le istanze di <xref:System.Drawing.Brush?displayProperty=nameWithType> , <xref:System.Drawing.Pen?displayProperty=nameWithType> e altre classi grafiche.</span><span class="sxs-lookup"><span data-stu-id="c813f-152">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class and instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="c813f-153">È importante creare una risorsa grafica solo quando è necessario e rilasciarla subito dopo averla usata.</span><span class="sxs-lookup"><span data-stu-id="c813f-153">It's important that you create a graphics resource only when you need it and release it soon as you're finished using it.</span></span> <span data-ttu-id="c813f-154">Se si crea un'istanza di un tipo che implementa l' <xref:System.IDisposable> interfaccia, chiamare il relativo <xref:System.IDisposable.Dispose%2A> metodo al termine dell'operazione per liberare risorse.</span><span class="sxs-lookup"><span data-stu-id="c813f-154">If you create an instance of a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you're finished with it to free resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="c813f-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c813f-155">See also</span></span>

- [<span data-ttu-id="c813f-156">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="c813f-156">Types of custom controls</span></span>](custom.md)
