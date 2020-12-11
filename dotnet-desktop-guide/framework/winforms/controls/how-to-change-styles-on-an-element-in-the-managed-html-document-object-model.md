---
title: 'Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 728bc77db959e25fe31d2ff37288b2359dca852e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962002"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito

È possibile usare gli stili in HTML per controllare l'aspetto di un documento e dei relativi elementi. <xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> supportano <xref:System.Windows.Forms.HtmlElement.Style%2A> le proprietà che accettano stringhe di stile nel formato seguente:

`name1:value1;...;nameN:valueN;`

Di seguito è riportato un oggetto `DIV` con una stringa di stile che imposta il tipo di carattere su Arial e tutto il testo in grassetto:

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

Il problema della manipolazione degli stili con la <xref:System.Windows.Forms.HtmlElement.Style%2A> proprietà è che può risultare complesso aggiungere e rimuovere le singole impostazioni di stile dalla stringa. Ad esempio, diventerebbe una procedura complessa per eseguire il rendering del testo precedente in corsivo ogni volta che l'utente posiziona il cursore su `DIV` e prende in corsivo quando il cursore esce dall'oggetto `DIV` . Il tempo diventa un problema se è necessario manipolare un numero elevato di stili in questo modo.

La procedura seguente contiene codice che è possibile usare per modificare facilmente gli stili su documenti ed elementi HTML. Per la procedura è necessario saper eseguire le attività di base in Windows Forms, ad esempio la creazione di un nuovo progetto e l'aggiunta di un controllo a un modulo.

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Per elaborare le modifiche di stile in un Windows Forms Application

1. Creare un nuovo progetto Windows Form.

2. Creare un nuovo file di classe che termina con l'estensione appropriata per il linguaggio di programmazione.

3. Copiare il `StyleGenerator` codice della classe nella sezione esempio di questo argomento nel file di classe e salvare il codice.

4. Salvare il codice HTML seguente in un file denominato Test.htm.

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. Aggiungere un <xref:System.Windows.Forms.WebBrowser> controllo denominato `webBrowser1` al form principale del progetto.

6. Aggiungere il codice seguente al file di codice del progetto.

    > [!IMPORTANT]
    > Verificare che il `webBrowser1_DocumentCompleted` gestore eventi sia configurato come listener per l' <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. In Visual Studio fare doppio clic sul <xref:System.Windows.Forms.WebBrowser> controllo; in un editor di testo, configurare il listener a livello di codice.

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. Eseguire il progetto. Eseguire il cursore sul primo `DIV` per osservare gli effetti del codice.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene illustrato il codice completo per la `StyleGenerator` classe, che analizza un valore di stile esistente, supporta l'aggiunta, la modifica e la rimozione di stili e restituisce un nuovo valore di stile con le modifiche richieste.

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.HtmlElement>
