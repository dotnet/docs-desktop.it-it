---
title: Panoramica dell'input del mouse
description: Informazioni sul funzionamento dell'input del mouse in Windows Forms per .NET. Gli eventi del mouse vengono generati da form e controlli e rappresentano lo stato della posizione e del pulsante del mouse.
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.openlocfilehash: 3e85305796d724d9acdbcd2e7cb86e748c30b783
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965878"
---
# <a name="overview-of-using-the-mouse-windows-forms-net"></a>Panoramica dell'uso del mouse (Windows Forms .NET)

La ricezione e la gestione di input del mouse è una parte importante di ogni applicazione Windows. È possibile gestire gli eventi del mouse per eseguire un'azione nell'applicazione oppure utilizzare le informazioni sulla posizione del mouse per eseguire hit testing o altre azioni. Inoltre, è possibile modificare il modo in cui i controlli dell'applicazione gestiscono l'input del mouse. In questo articolo vengono descritti in dettaglio questi eventi del mouse e viene illustrato come ottenere e modificare le impostazioni di sistema per il mouse.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

In Windows Forms l'input dell'utente viene inviato alle applicazioni sotto forma di [messaggi di Windows](/windows/win32/winmsg/about-messages-and-message-queues). Una serie di metodi sottoponibili a override elabora questi messaggi a livello di applicazione, di form e di controllo. Quando questi metodi ricevono messaggi del mouse, generano eventi che possono essere gestiti per ottenere informazioni sull'input del mouse. In molti casi, Windows Forms applicazioni possono elaborare tutti gli input utente semplicemente gestendo questi eventi. In altri casi, è possibile che un'applicazione esegua l'override di uno dei metodi che elaborano i messaggi per intercettare un determinato messaggio prima che venga ricevuto dall'applicazione, dal form o dal controllo.

## <a name="mouse-events"></a>Eventi del mouse

Tutti i controlli Windows Forms ereditano un set di eventi relativi all'input del mouse e della tastiera. Ad esempio, un controllo può gestire l' <xref:System.Windows.Forms.Control.MouseClick> evento per determinare la posizione di un clic del mouse. Per ulteriori informazioni sugli eventi del mouse, vedere [utilizzo degli eventi del](events.md)mouse.

## <a name="mouse-location-and-hit-testing"></a>Posizione del mouse e hit testing

Quando l'utente sposta il mouse, il sistema operativo sposta il puntatore del mouse. Il puntatore del mouse contiene un singolo pixel, denominato area sensibile, che il sistema operativo tiene traccia e riconosce come posizione dell'indicatore di misura. Quando l'utente sposta il mouse o preme un pulsante del mouse, l'oggetto <xref:System.Windows.Forms.Control> che contiene <xref:System.Windows.Forms.Cursor.HotSpot%2A> genera l'evento del mouse appropriato.

È possibile ottenere la posizione corrente del mouse con la <xref:System.Windows.Forms.MouseEventArgs.Location%2A> proprietà di <xref:System.Windows.Forms.MouseEventArgs> quando si gestisce un evento del mouse o utilizzando la <xref:System.Windows.Forms.Cursor.Position%2A> proprietà della <xref:System.Windows.Forms.Cursor> classe. È quindi possibile utilizzare le informazioni sulla posizione del mouse per eseguire hit testing, quindi eseguire un'azione in base alla posizione del mouse. La funzionalità di hit testing è incorporata in diversi controlli in Windows Forms, ad esempio i <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.MonthCalendar> controlli, e <xref:System.Windows.Forms.DataGridView> .

Usato con l'evento del mouse appropriato, <xref:System.Windows.Forms.Control.MouseHover> ad esempio, hit testing è molto utile per determinare quando l'applicazione deve eseguire un'azione specifica.

## <a name="changing-mouse-input-settings"></a>Modifica delle impostazioni di input del mouse

È possibile rilevare e modificare il modo in cui un controllo gestisce l'input del mouse derivando dal controllo e utilizzando i <xref:System.Windows.Forms.Control.GetStyle%2A> <xref:System.Windows.Forms.Control.SetStyle%2A> metodi e. Il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo accetta una combinazione bit per bit di <xref:System.Windows.Forms.ControlStyles> valori per determinare se il controllo avrà un clic standard, il comportamento di doppio clic o se il controllo gestirà la propria elaborazione del mouse. Inoltre, la <xref:System.Windows.Forms.SystemInformation> classe include le proprietà che descrivono le funzionalità del mouse e specificano il modo in cui il mouse interagisce con il sistema operativo. Nella tabella seguente sono riepilogate queste proprietà.

| Proprietà                                                               | Descrizione                                                                                                                                                            |
|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>       | Ottiene le dimensioni, in pixel, dell'area in cui l'utente deve fare clic due volte affinché il sistema operativo consideri i due clic come un doppio clic.                     |
| <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>       | Ottiene il numero massimo di millisecondi che possono trascorrere tra un primo clic e un secondo clic per fare in modo che l'azione del mouse venga considerata come un doppio clic. |
| <xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>          | Ottiene il numero di pulsanti del mouse.                                                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>   | Ottiene un valore che indica se le funzioni dei pulsanti sinistro e destro sono state invertite.                                                                   |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>        | Ottiene le dimensioni, in pixel, del rettangolo all'interno del quale il puntatore del mouse deve rimanere per l'intervallo di tempo richiesto perché sia generato un messaggio visualizzato al passaggio del mouse.        |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>        | Ottiene il tempo, in millisecondi, per il quale il puntatore del mouse deve soffermarsi nell'area rettangolare sensibile al passaggio del mouse prima che venga generato un messaggio.                                   |
| <xref:System.Windows.Forms.SystemInformation.MousePresent%2A>          | Ottiene un valore che indica se è installato un mouse.                                                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>            | Ottiene un valore che indica la velocità corrente del mouse, da 1 a 20.                                                                                                         |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>     | Ottiene un valore che indica se è installato un mouse con rotellina del mouse.                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A> | Ottiene la quantità del valore Delta dell'incremento di una singola rotazione della rotellina del mouse.                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A> | Ottiene il numero di righe da scorrere quando viene ruotata la rotellina del mouse.                                                                                                    |

## <a name="methods-that-process-user-input-messages"></a>Metodi che elaborano i messaggi di input dell'utente

I form e i controlli hanno accesso all' <xref:System.Windows.Forms.IMessageFilter> interfaccia e a un set di metodi sottoponibili a override che elaborano i messaggi di Windows in punti diversi della coda di messaggi. Tutti questi metodi hanno un <xref:System.Windows.Forms.Message> parametro che incapsula i dettagli di basso livello dei messaggi di Windows. È possibile implementare o eseguire l'override di questi metodi per esaminare il messaggio e quindi utilizzare il messaggio o passarlo al consumer successivo nella coda di messaggi. Nella tabella seguente vengono illustrati i metodi che elaborano tutti i messaggi di Windows in Windows Forms.

| Metodo     | Note |
|------------|-----------|
| <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A> | Questo metodo intercetta i messaggi di Windows accodati (noti anche come inviati) a livello di applicazione.|
| <xref:System.Windows.Forms.Control.PreProcessMessage%2A>       | Questo metodo intercetta i messaggi di Windows a livello di form e di controllo prima di essere elaborati.|
| <xref:System.Windows.Forms.Control.WndProc%2A>                 | Questo metodo elabora i messaggi di Windows a livello di form e di controllo.|
| <xref:System.Windows.Forms.Control.DefWndProc%2A>              | Questo metodo esegue l'elaborazione predefinita dei messaggi di Windows a livello di form e di controllo. In questo modo viene fornita la funzionalità minima di una finestra.|
| <xref:System.Windows.Forms.Control.OnNotifyMessage%2A>         | Questo metodo intercetta i messaggi a livello di form e di controllo, dopo che sono stati elaborati. <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage>Per chiamare questo metodo, è necessario impostare il bit di stile.|

## <a name="see-also"></a>Vedere anche

- [Utilizzo degli eventi del mouse (Windows Forms .NET)](events.md)
- [Panoramica sul comportamento del mouse di trascinamento della selezione (Windows Forms .NET)](drag-and-drop.md)
- [Gestire i puntatori del mouse (Windows Forms .NET)](how-to-manage-cursor-pointer.md)
