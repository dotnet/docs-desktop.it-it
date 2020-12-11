---
title: Eseguire il rendering di un controllo
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 86e219723dde8c10a8cc0d4ee7bdf149cde399bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964336"
---
# <a name="rendering-a-windows-forms-control"></a>Rendering di un controllo Windows Form

Il rendering si riferisce al processo di creazione di una rappresentazione visiva sullo schermo di un utente. Windows Forms utilizza GDI (la nuova libreria grafica di Windows) per il rendering. Le classi gestite che forniscono l'accesso a GDI si trovano nello <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi e nei relativi sottospazi dei nomi.  
  
 Per il rendering del controllo sono necessari gli elementi seguenti:  
  
- Funzionalità di disegno fornita dalla classe base <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .  
  
- Elementi essenziali della libreria grafica GDI.  
  
- Geometria dell'area di disegno.  
  
- Procedura per liberare risorse grafiche.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funzionalità di disegno fornita dal controllo  

 La classe base <xref:System.Windows.Forms.Control> fornisce la funzionalità di disegno tramite il relativo <xref:System.Windows.Forms.Control.Paint> evento. Un controllo genera l' <xref:System.Windows.Forms.Control.Paint> evento ogni volta che è necessario aggiornare la visualizzazione. Per ulteriori informazioni sugli eventi nel .NET Framework, vedere [gestione e generazione di eventi](/dotnet/standard/events/index).  
  
 La classe di dati dell'evento per l' <xref:System.Windows.Forms.Control.Paint> evento, <xref:System.Windows.Forms.PaintEventArgs> , include i dati necessari per il disegno di un controllo, ovvero un handle per un oggetto Graphics e un oggetto Rectangle che rappresenta l'area in cui disegnare. Questi oggetti vengono visualizzati in grassetto nel frammento di codice seguente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics> è una classe gestita che incapsula la funzionalità di disegno, come descritto nella discussione di GDI più avanti in questo argomento. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>È un'istanza della <xref:System.Drawing.Rectangle> struttura e definisce l'area disponibile in cui un controllo può essere disegnato. Uno sviluppatore del controllo può calcolare <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> usando la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di Geometry più avanti in questo argomento.  
  
 Un controllo deve fornire la logica di rendering eseguendo l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo da cui eredita <xref:System.Windows.Forms.Control> . <xref:System.Windows.Forms.Control.OnPaint%2A> Ottiene l'accesso a un oggetto Graphics e a un rettangolo da creare tramite l'oggetto <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> e le <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà dell' <xref:System.Windows.Forms.PaintEventArgs> istanza passata.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base <xref:System.Windows.Forms.Control> non implementa alcuna funzionalità di disegno, ma richiama solo i delegati dell'evento registrati con l' <xref:System.Windows.Forms.Control.Paint> evento. Quando si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> di, è in genere necessario richiamare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe base in modo che i delegati registrati ricevano l' <xref:System.Windows.Forms.Control.Paint> evento. Tuttavia, i controlli che disegnano l'intera superficie non devono richiamare la classe di base <xref:System.Windows.Forms.Control.OnPaint%2A> , in quanto introduce lo sfarfallio. Per un esempio di override dell' <xref:System.Windows.Forms.Control.OnPaint%2A> evento, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
> Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo, bensì richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> Metodo (Ereditato da <xref:System.Windows.Forms.Control> ) o un altro metodo che richiama <xref:System.Windows.Forms.Control.Invalidate%2A> . Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo richiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A> . Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo è sottoposto a overload e, a seconda degli argomenti forniti a <xref:System.Windows.Forms.Control.Invalidate%2A> `e` , un controllo ridisegnato una o tutte le relative aree dello schermo.  
  
 La <xref:System.Windows.Forms.Control> classe base definisce un altro metodo utile per il disegno, ovvero il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Disegna lo sfondo (e quindi la forma) della finestra ed è garantito che sia veloce, mentre <xref:System.Windows.Forms.Control.OnPaint%2A> Disegna i dettagli e potrebbe essere più lento perché le singole richieste di disegno vengono combinate in un unico <xref:System.Windows.Forms.Control.Paint> evento che copre tutte le aree che devono essere ridisegnate. Potrebbe essere necessario richiamare l'oggetto <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si desidera creare uno sfondo sfumato per il controllo.  
  
 Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ha una nomenclatura simile a un evento e accetta lo stesso argomento del `OnPaint` metodo, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> non è un vero metodo di evento. Non è presente alcun `PaintBackground` evento e non <xref:System.Windows.Forms.Control.OnPaintBackground%2A> richiama i delegati dell'evento. Quando si esegue l'override del <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo, non è necessaria una classe derivata per richiamare il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo della relativa classe di base.  
  
## <a name="gdi-basics"></a>Nozioni fondamentali su GDI+  

 La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare varie forme, ad esempio cerchi, triangoli, archi ed ellissi, nonché metodi per la visualizzazione di testo. Lo <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi e i relativi sottospazi dei nomi contengono classi che incapsulano elementi grafici come forme (cerchi, rettangoli, archi e altri), colori, tipi di carattere, pennelli e così via. Per ulteriori informazioni su GDI, vedere [utilizzo di classi grafiche gestite](../advanced/using-managed-graphics-classes.md). Le nozioni di base di GDI sono descritte anche in [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Geometria dell'area di disegno  

 La <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo specifica l'area rettangolare disponibile per il controllo sullo schermo dell'utente, mentre la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> specifica l'area effettivamente disegnata. Tenere presente che il disegno viene eseguito nel <xref:System.Windows.Forms.Control.Paint> metodo dell'evento che accetta un' <xref:System.Windows.Forms.PaintEventArgs> istanza come argomento. Un controllo potrebbe dover disegnare solo una parte dell'area disponibile, come nel caso in cui una piccola sezione della visualizzazione del controllo cambia. In questi casi, uno sviluppatore di controlli deve calcolare il rettangolo effettivo da creare e passarlo a <xref:System.Windows.Forms.Control.Invalidate%2A> . Le versioni di overload di <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un oggetto <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento usano tale argomento per generare la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> .  
  
 Nel frammento di codice seguente viene illustrato il modo `FlashTrackBar` in cui il controllo personalizzato calcola l'area rettangolare in cui eseguire il progetto. La `client` variabile denota la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Proprietà. Per un esempio completo, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberare risorse grafiche  

 Gli oggetti grafici sono costosi perché usano risorse di sistema. Tali oggetti includono le istanze della <xref:System.Drawing.Graphics?displayProperty=nameWithType> classe, nonché le istanze di <xref:System.Drawing.Brush?displayProperty=nameWithType> , <xref:System.Drawing.Pen?displayProperty=nameWithType> e altre classi grafiche. È importante creare una risorsa grafica solo quando è necessario e rilasciarla subito dopo averla usata. Se si crea un tipo che implementa l' <xref:System.IDisposable> interfaccia, chiamare il relativo <xref:System.IDisposable.Dispose%2A> metodo al termine dell'operazione per liberare risorse.  
  
 Nel frammento di codice seguente viene illustrato come il `FlashTrackBar` controllo personalizzato crea e rilascia una <xref:System.Drawing.Brush> risorsa. Per il codice sorgente completo, vedere [procedura: creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un controllo di Windows Forms che visualizzi lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md)
