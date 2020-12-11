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
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a>Disegno e disegno sui controlli (Windows Forms .NET)

Il disegno personalizzato dei controlli è una delle numerose attività complesse semplificate dal Windows Forms. Quando si crea un controllo personalizzato, sono disponibili molte opzioni per gestire l'aspetto grafico del controllo. Se si sta creando un [controllo personalizzato](custom.md#custom-controls), ovvero un controllo che eredita da <xref:System.Windows.Forms.Control> , è necessario fornire il codice per eseguire il rendering della relativa rappresentazione grafica.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Se si sta creando un [controllo composito](custom.md#composite-controls), ovvero un controllo che eredita da <xref:System.Windows.Forms.UserControl> o uno dei controlli Windows Forms esistenti, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice grafico.

Se si desidera fornire il rendering personalizzato per un controllo esistente senza creare un nuovo controllo, le opzioni diventano più limitate. Tuttavia, esiste ancora un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.

Per il rendering del controllo sono necessari gli elementi seguenti:

- Funzionalità di disegno fornita dalla classe base <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .
- Elementi essenziali della libreria grafica GDI.
- Geometria dell'area di disegno.
- Procedura per liberare risorse grafiche.

## <a name="drawing-provided-by-control"></a>Disegno fornito dal controllo

La classe base <xref:System.Windows.Forms.Control> fornisce la funzionalità di disegno tramite il relativo <xref:System.Windows.Forms.Control.Paint> evento. Un controllo genera l' <xref:System.Windows.Forms.Control.Paint> evento ogni volta che è necessario aggiornare la visualizzazione. Per ulteriori informazioni sugli eventi in .NET, vedere [gestione e generazione di eventi](/dotnet/standard/events/index).

La classe di dati dell'evento per l' <xref:System.Windows.Forms.Control.Paint> evento, <xref:System.Windows.Forms.PaintEventArgs> , include i dati necessari per il disegno di un handle di controllo in un oggetto Graphics e di un rettangolo che rappresenta l'area in cui disegnare.

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

<xref:System.Drawing.Graphics> è una classe gestita che incapsula la funzionalità di disegno, come descritto nella discussione di GDI più avanti in questo articolo. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>È un'istanza della <xref:System.Drawing.Rectangle> struttura e definisce l'area disponibile in cui un controllo può essere disegnato. Uno sviluppatore di controlli può calcolare <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> usando la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di geometria più avanti in questo articolo.

### <a name="onpaint"></a>OnPaint

Un controllo deve fornire la logica di rendering eseguendo l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo da cui eredita <xref:System.Windows.Forms.Control> . <xref:System.Windows.Forms.Control.OnPaint%2A> Ottiene l'accesso a un oggetto Graphics e a un rettangolo da creare tramite l'oggetto <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> e le <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà dell' <xref:System.Windows.Forms.PaintEventArgs> istanza passata.

Il codice seguente usa lo `System.Drawing` spazio dei nomi:

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base <xref:System.Windows.Forms.Control> non implementa alcuna funzionalità di disegno, ma richiama solo i delegati dell'evento registrati con l' <xref:System.Windows.Forms.Control.Paint> evento. Quando si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> di, è in genere necessario richiamare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe base in modo che i delegati registrati ricevano l' <xref:System.Windows.Forms.Control.Paint> evento. Tuttavia, i controlli che disegnano l'intera superficie non devono richiamare l'oggetto della classe di base <xref:System.Windows.Forms.Control.OnPaint%2A> , in quanto introduce lo sfarfallio.

> [!NOTE]
> Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo; richiamare invece il <xref:System.Windows.Forms.Control.Invalidate%2A> Metodo (Ereditato da <xref:System.Windows.Forms.Control> ) o un altro metodo che richiama <xref:System.Windows.Forms.Control.Invalidate%2A> . Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo richiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A> . Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo è sottoposto a overload e, a seconda degli argomenti forniti a <xref:System.Windows.Forms.Control.Invalidate%2A> `e` , ridisegnato una parte o tutta la relativa area dello schermo.

Il codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo verrà eseguito quando il controllo viene creato per la prima volta e ogni volta che viene aggiornato. Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a>OnPaintBackground

La <xref:System.Windows.Forms.Control> classe base definisce un altro metodo utile per il disegno, il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo.

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<xref:System.Windows.Forms.Control.OnPaintBackground%2A> Disegna lo sfondo (e, in questo modo, la forma) della finestra ed è garantito che sia veloce, mentre <xref:System.Windows.Forms.Control.OnPaint%2A> dipinge i dettagli e potrebbe essere più lento perché le singole richieste di disegno vengono combinate in un unico <xref:System.Windows.Forms.Control.Paint> evento che copre tutte le aree che devono essere ridisegnate. Potrebbe essere necessario richiamare l'oggetto <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si desidera creare uno sfondo sfumato per il controllo.

Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ha una nomenclatura simile a un evento e accetta lo stesso argomento del `OnPaint` metodo, `OnPaintBackground` non è un vero metodo di evento. Non è presente alcun `PaintBackground` evento e `OnPaintBackground` non richiama i delegati dell'evento. Quando si esegue l'override del `OnPaintBackground` metodo, non è necessaria una classe derivata per richiamare il `OnPaintBackground` metodo della relativa classe di base.

## <a name="gdi-basics"></a>Nozioni fondamentali su GDI+

La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare diverse forme, ad esempio cerchi, triangoli, archi ed ellissi e metodi per la visualizzazione di testo. Lo <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi contiene gli spazi dei nomi e le classi che incapsulano elementi grafici come forme (cerchi, rettangoli, archi e altri), colori, tipi di carattere, pennelli e così via.<!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a>Geometria dell'area di disegno

La <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo specifica l'area rettangolare disponibile per il controllo sullo schermo dell'utente, mentre la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> specifica l'area disegnata. Un controllo potrebbe dover disegnare solo una parte dell'area disponibile, come nel caso in cui una piccola sezione della visualizzazione del controllo cambia. In questi casi, uno sviluppatore di controlli deve calcolare il rettangolo effettivo da creare e passarlo a <xref:System.Windows.Forms.Control.Invalidate%2A> . Le versioni di overload di <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un oggetto <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento usano tale argomento per generare la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> .

## <a name="freeing-graphics-resources"></a>Liberare risorse grafiche

Gli oggetti grafici sono costosi perché usano risorse di sistema. Tali oggetti includono le istanze della <xref:System.Drawing.Graphics?displayProperty=nameWithType> classe e le istanze di <xref:System.Drawing.Brush?displayProperty=nameWithType> , <xref:System.Drawing.Pen?displayProperty=nameWithType> e altre classi grafiche. È importante creare una risorsa grafica solo quando è necessario e rilasciarla subito dopo averla usata. Se si crea un'istanza di un tipo che implementa l' <xref:System.IDisposable> interfaccia, chiamare il relativo <xref:System.IDisposable.Dispose%2A> metodo al termine dell'operazione per liberare risorse.

## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](custom.md)
