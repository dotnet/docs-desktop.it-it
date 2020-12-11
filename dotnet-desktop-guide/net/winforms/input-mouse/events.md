---
title: Utilizzo degli eventi del mouse
description: Panoramica dell'utilizzo degli eventi del mouse per gestire l'input del mouse. Ogni evento può fornire dati associati. Questo articolo fornisce un elenco di eventi correlati al mouse.
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Click event [Windows Forms]
- mouse [Windows Forms], mouse events
- Click event
- MouseClick event
- DoubleClick event
- MouseDown event
- MouseEnter event
- MouseHover event
- MouseLeave event
- MouseMove event
- MouseUp event
- MouseWheel event
- mouse events
- events [Windows Forms], mouse
ms.openlocfilehash: 84d3fc0ef8bca25defead65590d1e50369e628b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961087"
---
# <a name="using-mouse-events-windows-forms-net"></a>Utilizzo degli eventi del mouse (Windows Forms .NET)

La maggior parte dei Windows Forms programmi elaborano l'input del mouse gestendo gli eventi del mouse. In questo articolo viene fornita una panoramica degli eventi del mouse, inclusi i dettagli su quando utilizzare ogni evento e i dati forniti per ogni evento. Per ulteriori informazioni sugli eventi in generale, vedere [Cenni preliminari sugli eventi (Windows Forms .NET)](../forms/events.md).

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="mouse-events"></a>Eventi mouse

Il modo principale per rispondere all'input del mouse è quello di gestire gli eventi del mouse. Nella tabella seguente sono illustrati gli eventi del mouse e viene descritto quando vengono generati.

| Evento del mouse                                          | Descrizione                                             |
|------------------------------------------------------|---------------------------------------------------------|
| <xref:System.Windows.Forms.Control.Click>            | Questo evento si verifica quando viene rilasciato il pulsante del mouse, in genere prima dell' <xref:System.Windows.Forms.Control.MouseUp> evento. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando è necessario determinare solo quando si verifica un clic.                                                                             |
| <xref:System.Windows.Forms.Control.MouseClick>       | Questo evento si verifica quando l'utente fa clic sul controllo con il mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un clic.                                                                                                   |
| <xref:System.Windows.Forms.Control.DoubleClick>      | Questo evento si verifica quando si fa doppio clic sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>. Gestire questo evento quando è necessario determinare solo quando si verifica un doppio clic.                                                                                                                                             |
| <xref:System.Windows.Forms.Control.MouseDoubleClick> | Questo evento si verifica quando l'utente fa doppio clic sul controllo con il mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. Gestire questo evento quando è necessario ottenere informazioni sul mouse quando si verifica un doppio clic.                                                                                     |
| <xref:System.Windows.Forms.Control.MouseDown>        | Questo evento si verifica quando il puntatore del mouse si trova sul controllo e l'utente preme un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.                                                                                                                                                            |
| <xref:System.Windows.Forms.Control.MouseEnter>       | Questo evento si verifica quando il puntatore del mouse entra nel bordo o nell'area client del controllo, a seconda del tipo di controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.                                                                                                                                                     |
| <xref:System.Windows.Forms.Control.MouseHover>       | Questo evento si verifica quando il puntatore del mouse si arresta e si posiziona sul controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.                                                                                                                                                                                                      |
| <xref:System.Windows.Forms.Control.MouseLeave>       | Questo evento si verifica quando il puntatore del mouse esce dal bordo o dall'area client del controllo, a seconda del tipo del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.                                                                                                                                                 |
| <xref:System.Windows.Forms.Control.MouseMove>        | Questo evento si verifica quando il puntatore del mouse viene spostato mentre si trova su un controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.                                                                                                                                                                                   |
| <xref:System.Windows.Forms.Control.MouseUp>          | Questo evento si verifica quando il puntatore del mouse si trova sul controllo e l'utente rilascia un pulsante del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>.                                                                                                                                                           |
| <xref:System.Windows.Forms.Control.MouseWheel>       | Questo evento si verifica quando l'utente ruota la rotellina del mouse mentre il controllo ha lo stato attivo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.MouseEventArgs>. È possibile usare la <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> proprietà di <xref:System.Windows.Forms.MouseEventArgs> per determinare la distanza con cui il mouse è stato spostato. |

## <a name="mouse-information"></a>Informazioni del mouse

Un oggetto <xref:System.Windows.Forms.MouseEventArgs> viene inviato ai gestori degli eventi del mouse correlati alla pressione di un pulsante e alla registrazione dei movimenti del mouse. <xref:System.Windows.Forms.MouseEventArgs> fornisce informazioni sullo stato corrente del mouse, fra cui la posizione del puntatore nelle coordinate del client, i pulsanti del mouse premuti e se la rotellina del mouse è stata fatta scorrere. Diversi eventi del mouse, ad esempio quelli generati quando il puntatore del mouse è entrato o lasciato i limiti di un controllo, inviare un <xref:System.EventArgs> al gestore eventi senza ulteriori informazioni.

Se si desidera conoscere lo stato corrente dei pulsanti del mouse o la posizione del puntatore ed evitare la gestione di un evento del mouse, è anche possibile usare le proprietà <xref:System.Windows.Forms.Control.MouseButtons%2A> e <xref:System.Windows.Forms.Control.MousePosition%2A> della classe <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.MouseButtons%2A> restituisce informazioni sui pulsanti del mouse attualmente premuti. <xref:System.Windows.Forms.Control.MousePosition%2A> restituisce le coordinate dello schermo del puntatore del mouse e coincide con il valore restituito dalla proprietà <xref:System.Windows.Forms.Cursor.Position%2A>.

## <a name="converting-between-screen-and-client-coordinates"></a>Conversione tra coordinate dello schermo e del client

Poiché alcune informazioni sulla posizione del mouse sono espresse con le coordinate del client e altre con le coordinate dello schermo, può essere necessario eseguire una conversione da un sistema di coordinate all'altro. Questa operazione può essere eseguita facilmente usando i metodi <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibili nella classe <xref:System.Windows.Forms.Control>.

## <a name="standard-click-event-behavior"></a>Comportamento dell'evento Click standard

Se si vogliono gestire gli eventi Click del mouse nell'ordine corretto, è necessario conoscere l'ordine in cui gli eventi Click vengono generati nei controlli Windows Form. Tutti i controlli di Windows Forms generano eventi click nello stesso ordine quando viene premuto e rilasciato un pulsante del mouse supportato, tranne nei casi indicati nell'elenco seguente per i singoli controlli. L'ordine degli eventi generati per un singolo clic del pulsante del mouse è il seguente:

01. Evento<xref:System.Windows.Forms.Control.MouseDown> .
01. Evento<xref:System.Windows.Forms.Control.Click> .
01. Evento<xref:System.Windows.Forms.Control.MouseClick> .
01. Evento<xref:System.Windows.Forms.Control.MouseUp> .

Di seguito è riportato l'ordine degli eventi generati per un doppio clic del pulsante del mouse:

01. Evento<xref:System.Windows.Forms.Control.MouseDown> .
01. Evento<xref:System.Windows.Forms.Control.Click> .
01. Evento<xref:System.Windows.Forms.Control.MouseClick> .
01. Evento<xref:System.Windows.Forms.Control.MouseUp> .
01. Evento<xref:System.Windows.Forms.Control.MouseDown> .
01. Evento<xref:System.Windows.Forms.Control.DoubleClick> .

    Questo può variare a seconda che il controllo in questione abbia il <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> bit di stile impostato su `true` . Per ulteriori informazioni su come impostare un <xref:System.Windows.Forms.ControlStyles> bit, vedere il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo.

01. Evento<xref:System.Windows.Forms.Control.MouseDoubleClick> .
01. Evento<xref:System.Windows.Forms.Control.MouseUp> .

### <a name="individual-controls"></a>Singoli controlli

I controlli seguenti non sono conformi al comportamento standard dell'evento click del mouse:

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > Per il controllo <xref:System.Windows.Forms.ComboBox>, il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic sul campo di modifica, sul pulsante o su una voce dell'elenco.

  - **Clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Clic con pulsante destro**: nessun evento Click generato
  - **Doppio clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> ; <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Doppio clic con pulsante destro**: nessun evento Click generato

- Controlli <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> e <xref:System.Windows.Forms.CheckedListBox>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic in un punto qualsiasi di tali controlli.

  - **Clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Clic con pulsante destro**: nessun evento Click generato
  - **Doppio clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> , <xref:System.Windows.Forms.Control.DoubleClick> , <xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **Doppio clic con pulsante destro**: nessun evento Click generato

- Controllo <xref:System.Windows.Forms.ListView>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi nel controllo <xref:System.Windows.Forms.ListView>. Per i clic in altri punti del controllo non verranno generati eventi. Oltre agli eventi descritti di seguito esistono gli eventi <xref:System.Windows.Forms.ListView.BeforeLabelEdit> e <xref:System.Windows.Forms.ListView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.ListView>.

  - **Clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Clic con pulsante destro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Doppio clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> ; <xref:System.Windows.Forms.Control.DoubleClick> , <xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **Doppio clic con pulsante destro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> ; <xref:System.Windows.Forms.Control.DoubleClick> , <xref:System.Windows.Forms.Control.MouseDoubleClick>

- Controllo <xref:System.Windows.Forms.TreeView>

  > [!NOTE]
  > Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi stessi o a destra degli elementi nel controllo <xref:System.Windows.Forms.TreeView>. Per i clic in altri punti del controllo non verranno generati eventi. Oltre agli eventi descritti di seguito, esistono gli eventi <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> e <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.TreeView>.

  - **Clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Clic con pulsante destro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick>
  - **Doppio clic con pulsante sinistro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> ; <xref:System.Windows.Forms.Control.DoubleClick> , <xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **Doppio clic con pulsante destro**: <xref:System.Windows.Forms.Control.Click> , <xref:System.Windows.Forms.Control.MouseClick> ; <xref:System.Windows.Forms.Control.DoubleClick> , <xref:System.Windows.Forms.Control.MouseDoubleClick>

## <a name="painting-behavior-of-toggle-controls"></a>Comportamento del disegno dei controlli di attivazione/disimpostazione

I controlli di attivazione/disattivazione, quali quelli che derivano dalla classe <xref:System.Windows.Forms.ButtonBase>, presentano il seguente comportamento di disegno distintivo in combinazione con eventi Click del mouse:

01. L'utente preme il pulsante del mouse.
01. Il controllo viene disegnato nello stato premuto.
01. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseDown>.
01. L'utente rilascia il pulsante del mouse.
01. Il controllo viene disegnato nello stato generato.
01. Viene generato l'evento <xref:System.Windows.Forms.Control.Click>.
01. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseClick>.
01. Viene generato l'evento <xref:System.Windows.Forms.Control.MouseUp>.

    > [!NOTE]
    > Se l'utente sposta il puntatore all'esterno del controllo di attivazione/disattivazione mentre il pulsante del mouse è premuto, ad esempio spostando il mouse dal controllo <xref:System.Windows.Forms.Button> mentre il pulsante è premuto, il controllo di attivazione/disattivazione viene disegnato nello stato generato e si verifica solo l'evento <xref:System.Windows.Forms.Control.MouseUp>. In tale situazione l'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> non si verificherà.

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso del mouse (Windows Forms .NET)](overview.md)
- [Gestire i puntatori del mouse (Windows Forms .NET)](how-to-manage-cursor-pointer.md)
- [Come simulare gli eventi del mouse (Windows Forms .NET)](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>
