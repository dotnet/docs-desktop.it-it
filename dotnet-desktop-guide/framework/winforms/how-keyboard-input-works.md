---
title: Funzionamento dell'input da tastiera
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: aafc7b27cdd2d4c9c013a1f9632ee68ab2364dcd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951382"
---
# <a name="how-keyboard-input-works"></a>Funzionamento dell'input da tastiera

Windows Forms elabora gli input della tastiera generando eventi di tastiera in risposta ai messaggi di Windows. La maggioranza delle applicazioni Windows Forms elabora gli input della tastiera tramite la gestione dei relativi eventi. Tuttavia è necessario conoscere il funzionano dei messaggi della tastiera per poter implementare scenari più avanzati di input dalla tastiera, ad esempio l'intercettazione dei tasti prima che raggiungano un controllo. Questo argomento descrive i tipi di dati di tasti che Windows Forms riconosce e fornisce una panoramica del modo in cui vengono instradati i messaggi della tastiera. Per informazioni sugli eventi della tastiera, vedere [Utilizzo degli eventi di tastiera](using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Tipi di tasti  

 Windows Forms identifica l'input da tastiera come codici chiave virtuale rappresentati dall'enumerazione bit per bit <xref:System.Windows.Forms.Keys> . Con l' <xref:System.Windows.Forms.Keys> enumerazione è possibile combinare una serie di tasti premuti per generare un singolo valore. Questi valori corrispondono ai valori che accompagnano i messaggi di Windows WM_KEYDOWN e WM_SYSKEYDOWN. È possibile rilevare la maggior parte delle pressioni della chiave fisica gestendo gli <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.Control.KeyUp> eventi o. I tasti di tipo carattere sono un subset dell' <xref:System.Windows.Forms.Keys> enumerazione e corrispondono ai valori che accompagnano i messaggi di WM_CHAR e WM_SYSCHAR Windows. Se la combinazione di tasti premuti restituisce un carattere, è possibile rilevare il carattere gestendo l' <xref:System.Windows.Forms.Control.KeyPress> evento. In alternativa, è possibile usare <xref:Microsoft.VisualBasic.Devices.Keyboard> , esposto da Visual Basic interfaccia di programmazione, per individuare i tasti premuti e inviare i tasti. Per altre informazioni, vedere [Accesso alla tastiera](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar).  
  
## <a name="order-of-keyboard-events"></a>Ordine degli eventi di tastiera  

 Come indicato in precedenza, ci sono 3 eventi correlati alla tastiera che possono verificarsi in un controllo. La sequenza seguente illustra l'ordine generale degli eventi:  
  
1. L'utente inserisce il tasto "a", il tasto viene pre-elaborato, inviato e <xref:System.Windows.Forms.Control.KeyDown> si verifica un evento.  
  
2. L'utente possiede la chiave "a", la chiave viene pre-elaborata, inviata e <xref:System.Windows.Forms.Control.KeyPress> si verifica un evento.  
  
     Questo evento si verifica più volte quando l'utente tiene premuto un tasto.  
  
3. L'utente rilascia il tasto "a", il tasto viene pre-elaborato, inviato e <xref:System.Windows.Forms.Control.KeyUp> si verifica un evento.  
  
## <a name="preprocessing-keys"></a>Pre-elaborazione dei tasti  

 Analogamente ad altri messaggi, i messaggi della tastiera vengono elaborati nel <xref:System.Windows.Forms.Control.WndProc%2A> metodo di un form o di un controllo. Tuttavia, prima dell'elaborazione dei messaggi della tastiera, il <xref:System.Windows.Forms.Control.PreProcessMessage%2A> metodo chiama uno o più metodi di cui è possibile eseguire l'override per gestire chiavi di caratteri speciali e chiavi fisiche. È possibile eseguire l'override di questi metodi per rilevare e filtrare alcuni tasti prima che i messaggi vengano elaborati dal controllo. La tabella seguente mostra l'azione che viene eseguita e il relativo metodo correlato che si verifica, nell'ordine in cui il metodo si verifica.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Pre-elaborazione per un evento KeyDown  
  
|Azione|Metodo correlato|Note|  
|------------|--------------------|-----------|  
|Cercare un tasto di comando, ad esempio un tasto acceleratore o un tasto di menu di scelta rapida.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Questo metodo elabora un tasto di comando, che ha la precedenza sui tasti normali. Se questo metodo restituisce `true`, il messaggio del tasto non viene inviato e non si verifica alcun evento del tasto. Se restituisce `false` , <xref:System.Windows.Forms.Control.IsInputKey%2A> viene chiamato il metodo`.`|  
|Verificare la presenza di un tasto speciale che richiede la pre-elaborazione o una chiave di carattere normale che deve generare un <xref:System.Windows.Forms.Control.KeyDown> evento e che deve essere inviata a un controllo.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Se il metodo restituisce `true` , significa che il controllo è un carattere normale e <xref:System.Windows.Forms.Control.KeyDown> viene generato un evento. Se `false` , <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> viene chiamato il metodo. **Nota:**  Per garantire che un controllo ottenga una chiave o una combinazione di chiavi, è possibile gestire l' <xref:System.Windows.Forms.Control.PreviewKeyDown> evento e il set <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> di <xref:System.Windows.Forms.PreviewKeyDownEventArgs> a `true` per la chiave o i tasti desiderati.|  
|Cercare un tasto di spostamento (ESC, TAB, INVIO o tasti di direzione).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Questo metodo elabora un tasto fisico che impiega funzionalità speciali all'interno del controllo, ad esempio spostando lo stato attivo tra il controllo e il relativo elemento padre. Se il controllo immediato non gestisce la chiave, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> viene chiamato sul controllo padre e così via fino al controllo più in alto nella gerarchia. Se questo metodo restituisce `true`, la pre-elaborazione è completa e non viene generato alcun evento di tasto. Se restituisce `false` , <xref:System.Windows.Forms.Control.KeyDown> si verifica un evento.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Pre-elaborazione per un evento KeyPress  
  
|Azione|Metodo correlato|Note|  
|------------|--------------------|-----------|  
|Verificare se il tasto è un carattere normale che deve essere elaborato dal controllo|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Se il carattere è un carattere normale, questo metodo restituisce `true` , <xref:System.Windows.Forms.Control.KeyPress> viene generato l'evento e non viene eseguita alcuna ulteriore elaborazione. In caso contrario <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> , verrà chiamato.|  
|Verificare se il carattere è un tasto di scelta (ad esempio &OK su un pulsante)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Questo metodo, simile a <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> , verrà denominato gerarchia dei controlli. Se il controllo è un controllo contenitore, verifica i tasti di scelta chiamando <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> su se stesso e i relativi controlli figlio. Se <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> restituisce `true` , <xref:System.Windows.Forms.Control.KeyPress> non si verifica alcun evento.|  
  
## <a name="processing-keyboard-messages"></a>Elaborazione dei messaggi della tastiera  

 Dopo che i messaggi della tastiera raggiungono il <xref:System.Windows.Forms.Control.WndProc%2A> metodo di un form o di un controllo, vengono elaborati da un set di metodi di cui è possibile eseguire l'override. Ognuno di questi metodi restituisce un <xref:System.Boolean> valore che specifica se il messaggio della tastiera è stato elaborato e utilizzato dal controllo. Se uno dei metodi restituisce `true`, il messaggio viene considerato gestito e non viene passato alla base o all'elemento padre del controllo per un'ulteriore elaborazione. In caso contrario il messaggio rimane nella coda dei messaggi e può essere elaborato in un altro metodo nella base o nell'elemento padre del controllo. La tabella seguente presenta i metodi che elaborano i messaggi della tastiera.  
  
|Metodo|Note|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Questo metodo elabora tutti i messaggi della tastiera ricevuti dal <xref:System.Windows.Forms.Control.WndProc%2A> metodo del controllo.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Questo metodo invia il messaggio della tastiera all'elemento padre del controllo. Se <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> restituisce `true` , non viene generato alcun evento di chiave; in caso contrario, <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> viene chiamato.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Questo metodo genera gli <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.Control.KeyPress> eventi, e <xref:System.Windows.Forms.Control.KeyUp> , a seconda dei casi.|  
  
## <a name="overriding-keyboard-methods"></a>Override dei metodi della tastiera  

 Sono disponibili molti metodi di cui eseguire l'override quando un messaggio della tastiera viene pre-elaborato ed elaborato, tuttavia alcuni metodi sono preferibili ad altri. La tabella seguente mostra le attività che è possibile eseguire e il modo migliore per eseguire l'override dei metodi della tastiera. Per ulteriori informazioni sull'override dei metodi, vedere [override di proprietà e metodi nelle classi derivate](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics#overriding-properties-and-methods-in-derived-classes).  
  
|Attività|Metodo|  
|----------|------------|  
|Intercettare un tasto di spostamento e generare un <xref:System.Windows.Forms.Control.KeyDown> evento. Ad esempio si desidera che TAB e INVIO siano gestiti in una casella di testo.|Eseguire l'override di <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Nota:**  In alternativa, è possibile gestire l' <xref:System.Windows.Forms.Control.PreviewKeyDown> evento e il set <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> di <xref:System.Windows.Forms.PreviewKeyDownEventArgs> a `true` per la chiave o i tasti desiderati.|  
|Eseguire la gestione di input speciali o dello spostamento su un controllo. Ad esempio si desidera che l'uso dei tasti di direzione nel controllo elenco cambi la voce selezionata.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Intercettare un tasto di spostamento e generare un <xref:System.Windows.Forms.Control.KeyPress> evento. Ad esempio in un controllo casella di selezione si desidera che più pressioni di un tasto di direzione accelerino lo spostamento tra le voci.|Eseguire l'override di <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Esegue una gestione speciale di input o navigazione durante un <xref:System.Windows.Forms.Control.KeyPress> evento. Ad esempio, in un controllo elenco, tenendo premuto il tasto "r" si passa fra le voci che iniziano con la lettera r.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Eseguire una gestione personalizzata dei tasti di scelta; ad esempio, si desidera gestire i tasti di scelta sui pulsanti disegnati dal proprietario contenuti in una barra degli strumenti.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [Oggetto My.Computer.Keyboard](/dotnet/visual-basic/language-reference/objects/my-computer-keyboard-object)
- [Accesso alla tastiera](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar)
- [Utilizzo degli eventi di tastiera](using-keyboard-events.md)
