---
title: "Procedura: Implementare comunicazioni bidirezionali tra il codice DHTML e il codice dell'applicazione client"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 26cbc995a749c4c129729be700dee588d1033a05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965116"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a>Procedura: Implementare comunicazioni bidirezionali tra il codice DHTML e il codice dell'applicazione client

È possibile usare il controllo <xref:System.Windows.Forms.WebBrowser> per aggiungere codice HTML dinamico (DHTML) dell'applicazione Web esistente alle applicazioni client Windows Form. Questa procedura è utile quando in fase di sviluppo si è investito molto tempo nella creazione di controlli basati su DHTML e si desidera usufruire di tutte le capacità offerte dall'interfaccia utente di Windows Form senza dover riscrivere il codice esistente.

Il controllo <xref:System.Windows.Forms.WebBrowser> consente di implementare comunicazioni bidirezionali tra il codice dell'applicazione client e il codice di script della pagina Web mediante le proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> e <xref:System.Windows.Forms.WebBrowser.Document%2A>. È anche possibile configurare il controllo <xref:System.Windows.Forms.WebBrowser> in modo da poter unire senza problemi i controlli Web agli altri controlli del form dell'applicazione, nascondendo la relativa implementazione DHTML. A questo scopo, è sufficiente formattare la pagina visualizzata in modo che il colore di sfondo e lo stile visivo corrispondano al resto del form e usare le proprietà <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> e <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> per disabilitare le funzionalità standard del browser.

## <a name="to-embed-dhtml-in-your-windows-forms-application"></a>Per incorporare il codice DHTML in un'applicazione Windows Forms

1. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser> del controllo <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> su `false` per impedire a <xref:System.Windows.Forms.WebBrowser> di aprire i file rilasciati nel controllo.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]

2. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> del controllo su `false` per impedire la visualizzazione del menu di scelta rapida di <xref:System.Windows.Forms.WebBrowser> quando l'utente fa clic con il pulsante destro del mouse sul controllo.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]

3. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> del controllo su `false` per impedire che il controllo <xref:System.Windows.Forms.WebBrowser> risponda ai tasti di scelta rapida.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]

4. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> nel costruttore del form o in un gestore eventi <xref:System.Windows.Forms.Form.Load>.

     Il codice seguente usa la classe del form per l'oggetto script.

    > [!NOTE]
    > È necessario che Component Object Model (COM) possa accedere all'oggetto script. Per rendere visibile il form a COM, aggiungere l'attributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> alla classe del form.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]

5. Implementare proprietà o metodi pubblici nel codice dell'applicazione che verrà usato dal codice di script.

     Se ad esempio si usa la classe del form per l'oggetto script, aggiungere alla classe il codice seguente.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]

6. Usare l'oggetto `window.external` nel codice di script per accedere alle proprietà e ai metodi pubblici dell'oggetto specificato.

     Il codice HTML riportato di seguito dimostra come chiamare un metodo nell'oggetto script in seguito alla selezione di un pulsante. Copiare questo codice nell'elemento BODY di un documento HTML che è stato caricato mediante il metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del controllo o a cui è stata assegnata la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo.

    ```html
    <button onclick="window.external.Test('called from script code')">
        call client code from script code
    </button>
    ```

7. Implementare funzioni nel codice di script che verrà usato dal codice dell'applicazione.

     L'elemento SCRIPT HTML riportato di seguito fornisce una funzione di esempio. Copiare questo codice nell'elemento HEAD di un documento HTML che è stato caricato mediante il metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del controllo o a cui è stata assegnata la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo.

    ```html
    <script>
    function test(message) {
        alert(message);
    }
    </script>
    ```

8. Usare la proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> per accedere al codice di script dal codice dell'applicazione client.

     Ad esempio, aggiungere il codice seguente al gestore eventi di un pulsante <xref:System.Windows.Forms.Control.Click>.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]

9. Una volta terminato il debug del codice DHTML, impostare la proprietà <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> del controllo su `true` per impedire al controllo <xref:System.Windows.Forms.WebBrowser> di visualizzare messaggi di errore in caso di problemi nel codice di script.

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]

## <a name="example"></a>Esempio

L'esempio di codice completo riportato di seguito illustra un'applicazione di prova che può essere usata per comprendere meglio questa funzionalità. Anziché essere caricato da un file HTML separato, il codice HTML viene caricato nel controllo <xref:System.Windows.Forms.WebBrowser> mediante la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.

[!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]

## <a name="compiling-the-code"></a>Compilazione del codice

Per questo codice sono necessari i requisiti seguenti:

- Riferimenti agli assembly System e System.Windows.Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [Controllo WebBrowser](webbrowser-control-windows-forms.md)
