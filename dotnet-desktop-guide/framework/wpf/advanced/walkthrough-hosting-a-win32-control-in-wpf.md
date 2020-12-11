---
title: Ospitare un controllo Win32 in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 257e75522e598ce3eeb005290dcd0cd7d4910706
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967375"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Procedura dettagliata: ospitare un controllo Win32 in WPF
Windows Presentation Foundation (WPF) fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale nel codice Win32, potrebbe essere più efficace riutilizzare almeno parte del codice nell'applicazione WPF anziché riscriverlo completamente. WPF fornisce un meccanismo semplice per l'hosting di una finestra Win32, in una pagina WPF.  
  
 In questo argomento viene illustrata un'applicazione che ospita un controllo [ListBox Win32 nell'esempio WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)che ospita un controllo casella di riepilogo Win32. Questa procedura generale può essere estesa per ospitare qualsiasi finestra di Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Requisiti  
 In questo argomento si presuppone una conoscenza di base di WPF e della programmazione dell'API Windows. Per un'introduzione di base alla programmazione WPF, vedere [Introduzione](../getting-started/index.md). Per un'introduzione alla programmazione dell'API Windows, vedere uno dei numerosi libri sull'argomento, in particolare *programmare Windows* di Charles Petzold.  
  
 Poiché l'esempio che accompagna questo argomento viene implementato in C#, USA i servizi di chiamata della piattaforma (PInvoke) per accedere all'API Windows. Una certa familiarità con PInvoke è utile ma non essenziale.  
  
> [!NOTE]
> Questo argomento include vari esempi di codice tratti dall'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. È possibile ottenere o visualizzare il codice completo dall' [hosting di un controllo ListBox Win32 nell'esempio WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Procedura di base  
 Questa sezione descrive la procedura di base per l'hosting di una finestra Win32 in una pagina WPF. Le sezioni rimanenti illustrano in dettaglio i vari passaggi.  
  
 La procedura di hosting base è la seguente:  
  
1. Implementare una pagina WPF per ospitare la finestra. Una tecnica consiste nel creare un <xref:System.Windows.Controls.Border> elemento per riservare una sezione della pagina per la finestra ospitata.  
  
2. Implementare una classe per ospitare il controllo che eredita da <xref:System.Windows.Interop.HwndHost> .  
  
3. In tale classe, eseguire l'override del <xref:System.Windows.Interop.HwndHost> membro della classe <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> .  
  
4. Creare la finestra ospitata come figlio della finestra che contiene la pagina WPF. Sebbene la programmazione WPF convenzionale non debba utilizzarla in modo esplicito, la pagina di hosting è una finestra con un handle (HWND). Si riceve la pagina HWND tramite il `hwndParent` parametro del <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> metodo. La finestra ospitata deve essere creata come elemento figlio dell'oggetto HWND.  
  
5. Dopo aver creato la finestra host, restituire l'oggetto HWND della finestra ospitata. Se si desidera ospitare uno o più controlli Win32, in genere si crea una finestra host come elemento figlio di HWND e si rendono i controlli figlio di tale finestra host. Il wrapping dei controlli in una finestra host offre un modo semplice per la ricezione delle notifiche dai controlli da parte della pagina WPF, che riguarda alcuni problemi Win32 specifici con le notifiche attraverso il limite HWND.  
  
6. Gestire i messaggi selezionati inviati alla finestra host, ad esempio notifiche dai controlli figlio. Per eseguire questa operazione è possibile procedere in due modi:  
  
    - Se si preferisce gestire i messaggi nella classe host, eseguire l'override del <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodo della <xref:System.Windows.Interop.HwndHost> classe.  
  
    - Se si preferisce che WPF gestisca i messaggi, gestire l' <xref:System.Windows.Interop.HwndHost> evento della classe <xref:System.Windows.Interop.HwndHost.MessageHook> nel code-behind. Questo evento si verifica per ogni messaggio ricevuto dalla finestra ospitata. Se si sceglie questa opzione, è comunque necessario eseguire l'override di <xref:System.Windows.Interop.HwndHost.WndProc%2A> , ma è necessaria solo un'implementazione minima.  
  
7. Eseguire l'override dei <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodi e di <xref:System.Windows.Interop.HwndHost> . Per soddisfare il contratto, è necessario eseguire l'override di questi metodi <xref:System.Windows.Interop.HwndHost> , ma potrebbe essere necessario fornire solo un'implementazione minima.  
  
8. Nel file code-behind creare un'istanza della classe di hosting del controllo e impostarla come figlio dell' <xref:System.Windows.Controls.Border> elemento destinato a ospitare la finestra.  
  
9. Comunicare con la finestra ospitata inviando i messaggi di Microsoft Windows e gestendo i messaggi dalle relative finestre figlio, ad esempio le notifiche inviate dai controlli.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>Implementare il layout di pagina  
 Il layout per la pagina WPF che ospita il controllo ListBox è costituito da due aree. Il lato sinistro della pagina ospita diversi controlli WPF che forniscono un oggetto [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] che consente di modificare il controllo Win32. L'angolo superiore destro della pagina include un'area quadrata per il controllo ListBox ospitato.  
  
 Il codice per implementare questo layout è piuttosto semplice. L'elemento radice è un oggetto <xref:System.Windows.Controls.DockPanel> che dispone di due elementi figlio. Il primo è un <xref:System.Windows.Controls.Border> elemento che ospita il controllo ListBox. Occupa un quadrato 200x200 nell'angolo superiore destro della pagina. Il secondo è un <xref:System.Windows.Controls.StackPanel> elemento che contiene un set di controlli WPF che visualizzano informazioni e consentono di modificare il controllo ListBox impostando le proprietà di interoperatività esposte. Per ogni elemento figlio di <xref:System.Windows.Controls.StackPanel> , vedere il materiale di riferimento per i vari elementi utilizzati per informazioni dettagliate su questi elementi o sul loro funzionamento. questi elementi sono elencati nel codice di esempio riportato di seguito, ma non verranno illustrati in questo articolo (il modello di interoperatività di base non ne richiede alcuno, viene fornito per aggiungere alcune interattività all'esempio).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementare una classe per l'hosting del controllo Microsoft Win32  
 La parte centrale di questo esempio è la classe che ospita effettivamente il controllo, ControlHost.cs. Eredita da <xref:System.Windows.Interop.HwndHost>. Il costruttore accetta due parametri, Height e Width, che corrispondono all'altezza e alla larghezza dell' <xref:System.Windows.Controls.Border> elemento che ospita il controllo ListBox. Questi valori vengono usati in un secondo momento per garantire che la dimensione del controllo corrisponda all' <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 È anche presente un insieme di costanti. Queste costanti vengono ricavate principalmente da winuser. h e consentono di usare nomi convenzionali quando si chiamano funzioni Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Eseguire l'override di BuildWindowCore per creare la finestra Microsoft Win32  
 È possibile eseguire l'override di questo metodo per creare la finestra Win32 che verrà ospitata dalla pagina e per effettuare la connessione tra la finestra e la pagina. Poiché questo esempio include l'hosting di un controllo ListBox vengono create due finestre. Il primo è la finestra che è effettivamente ospitata dalla pagina WPF. Il controllo ListBox viene creato come elemento figlio di questa finestra.  
  
 Lo scopo di questo approccio è semplificare il processo di ricezione di notifiche dal controllo. La <xref:System.Windows.Interop.HwndHost> classe consente di elaborare i messaggi inviati alla finestra ospitata. Se si ospita un controllo Win32 direttamente, vengono ricevuti i messaggi inviati al ciclo di messaggi interno del controllo. È possibile visualizzare il controllo e inviare a esso messaggi ma non ricevere le notifiche che il controllo invia alla propria finestra padre. Ciò significa, tra l'altro, che non è possibile in alcun modo rilevare quando l'utente interagisce con il controllo. Creare invece una finestra host e impostare il controllo come elemento figlio di tale finestra. Ciò consente di elaborare i messaggi per la finestra host, incluse le notifiche inviate a essa dal controllo. Per comodità, dal momento che la finestra host è poco più di un semplice wrapper per il controllo, il pacchetto verrà restituito come un controllo ListBox.  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>Creare la finestra host e il controllo ListBox  
 È possibile utilizzare PInvoke per creare una finestra host per il controllo creando e registrando una classe della finestra e così via. Tuttavia, un approccio molto più semplice consiste nel creare una finestra con la classe della finestra "statica" predefinita. Questo approccio rende disponibile la procedura della finestra necessaria per ricevere le notifiche dal controllo e richiede codice minimo.  
  
 L'oggetto HWND del controllo è esposto tramite una proprietà di sola lettura di modo che la pagina host possa usarlo per inviare messaggi al controllo.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Il controllo ListBox viene creato come elemento figlio della finestra host. L'altezza e la larghezza di entrambe le finestre sono impostate sui valori passati dal costruttore, come illustrato in precedenza. Ciò garantisce che le dimensioni della finestra host e del controllo siano identiche all'area riservata nella pagina.  Una volta create le finestre, l'esempio restituisce un <xref:System.Runtime.InteropServices.HandleRef> oggetto che contiene l'HWND della finestra host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>Implementare DestroyWindow e WndProc  
 Oltre a <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> , è inoltre necessario eseguire l'override <xref:System.Windows.Interop.HwndHost.WndProc%2A> dei <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> metodi e di <xref:System.Windows.Interop.HwndHost> . In questo esempio, i messaggi per il controllo vengono gestiti dal <xref:System.Windows.Interop.HwndHost.MessageHook> gestore, pertanto l'implementazione di <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> è minima. Nel caso di <xref:System.Windows.Interop.HwndHost.WndProc%2A> , impostare `handled` su `false` per indicare che il messaggio non è stato gestito e restituire 0. Per <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> , eliminare semplicemente la finestra.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>Ospitare il controllo nella pagina  
 Per ospitare il controllo nella pagina, creare prima di tutto una nuova istanza della `ControlHost` classe. Passare l'altezza e la larghezza dell'elemento Border che contiene il controllo ( `ControlHostElement` ) al `ControlHost` costruttore. Questo garantisce che le dimensioni di ListBox siano corrette. È quindi possibile ospitare il controllo nella pagina assegnando l' `ControlHost` oggetto alla <xref:System.Windows.Controls.Decorator.Child%2A> proprietà dell'host <xref:System.Windows.Controls.Border> .  
  
 L'esempio connette un gestore all' <xref:System.Windows.Interop.HwndHost.MessageHook> evento di `ControlHost` per ricevere messaggi dal controllo. Questo evento viene generato per ogni messaggio inviato alla finestra ospitata. In questo caso, si tratta dei messaggi inviati alla finestra che esegue il wrapping del controllo ListBox effettivo, incluse le notifiche dal controllo. L'esempio chiama SendMessage per ottenere informazioni dal controllo e ne modifica il contenuto. I dettagli di come la pagina comunica con il controllo sono illustrati nella sezione successiva.  
  
> [!NOTE]
> Si noti che sono presenti due dichiarazioni PInvoke per SendMessage. Questa operazione è necessaria perché si usa il `wParam` parametro per passare una stringa e l'altra la usa per passare un numero intero. È necessaria una dichiarazione separata per ogni firma per assicurare che venga eseguito correttamente il marshalling dei dati.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementare la comunicazione tra il controllo e la pagina  
 Il controllo viene modificato inviando messaggi di Windows. Il controllo comunica quando l'utente interagisce con esso inviando notifiche alla propria finestra host. L'esempio che [ospita un controllo ListBox Win32 in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) include un'interfaccia utente che fornisce diversi esempi di funzionamento:  
  
- Accodare un elemento all'elenco.  
  
- Eliminare l'elemento selezionato dall'elenco.  
  
- Visualizzare il testo dell'elemento attualmente selezionato.  
  
- Visualizzare il numero di elementi nell'elenco.  
  
 L'utente può anche selezionare un elemento nella casella di riepilogo facendo clic su di esso, così come per un'applicazione Win32 convenzionale. I dati visualizzati vengono aggiornati ogni vota che l'utente modifica lo stato della casella di riepilogo, selezionando, aggiungendo o accodando un elemento.  
  
 Per accodare elementi, inviare alla casella di riepilogo un [ `LB_ADDSTRING` messaggio](/windows/desktop/Controls/lb-addstring). Per eliminare gli elementi, inviare [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) per ottenere l'indice della selezione corrente e quindi [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) per eliminare l'elemento. L'esempio invia anche [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount) e usa il valore restituito per aggiornare la visualizzazione che mostra il numero di elementi. Entrambe le istanze di [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) utilizzano una delle dichiarazioni PInvoke illustrate nella sezione precedente.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Quando l'utente seleziona un elemento o ne modifica la selezione, il controllo notifica alla finestra host inviando un [ `WM_COMMAND` messaggio](/windows/desktop/menurc/wm-command), che genera l' <xref:System.Windows.Interop.HwndHost.MessageHook> evento per la pagina. Il gestore riceve le stesse informazioni della routine della finestra principale della finestra host. Passa inoltre un riferimento a un valore booleano `handled` . Impostare `handled` su `true` per indicare che il messaggio è stato gestito e che non sono necessarie ulteriori elaborazioni.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) viene inviato per diversi motivi, pertanto è necessario esaminare l'ID notifica per determinare se si tratta di un evento che si desidera gestire. L'ID è contenuto nel Word superiore del `wParam` parametro. Nell'esempio vengono utilizzati operatori bit per bit per estrarre l'ID. Se l'utente ha apportato o modificato la selezione, l'ID sarà [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) .  
  
 Quando [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) viene ricevuto, l'esempio ottiene l'indice dell'elemento selezionato inviando al controllo un [ `LB_GETCURSEL` messaggio](/windows/desktop/Controls/lb-getcursel). Per ottenere il testo, creare prima un oggetto <xref:System.Text.StringBuilder> . Il controllo viene quindi inviato a un [ `LB_GETTEXT` messaggio](/windows/desktop/Controls/lb-gettext). Passare l' <xref:System.Text.StringBuilder> oggetto vuoto come `wParam` parametro. Quando [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) restituisce, il conterrà <xref:System.Text.StringBuilder> il testo dell'elemento selezionato. Questo utilizzo di [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) richiede ancora un'altra dichiarazione PInvoke.  
  
 Infine, impostare `handled` su `true` per indicare che il messaggio è stato gestito.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndHost>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Procedura dettagliata: Compilare una prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
