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
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="8806b-102">Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="8806b-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="8806b-103">È possibile usare gli stili in HTML per controllare l'aspetto di un documento e dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="8806b-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="8806b-104"><xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> supportano <xref:System.Windows.Forms.HtmlElement.Style%2A> le proprietà che accettano stringhe di stile nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8806b-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>

`name1:value1;...;nameN:valueN;`

<span data-ttu-id="8806b-105">Di seguito è riportato un oggetto `DIV` con una stringa di stile che imposta il tipo di carattere su Arial e tutto il testo in grassetto:</span><span class="sxs-lookup"><span data-stu-id="8806b-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

<span data-ttu-id="8806b-106">Il problema della manipolazione degli stili con la <xref:System.Windows.Forms.HtmlElement.Style%2A> proprietà è che può risultare complesso aggiungere e rimuovere le singole impostazioni di stile dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="8806b-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="8806b-107">Ad esempio, diventerebbe una procedura complessa per eseguire il rendering del testo precedente in corsivo ogni volta che l'utente posiziona il cursore su `DIV` e prende in corsivo quando il cursore esce dall'oggetto `DIV` .</span><span class="sxs-lookup"><span data-stu-id="8806b-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="8806b-108">Il tempo diventa un problema se è necessario manipolare un numero elevato di stili in questo modo.</span><span class="sxs-lookup"><span data-stu-id="8806b-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>

<span data-ttu-id="8806b-109">La procedura seguente contiene codice che è possibile usare per modificare facilmente gli stili su documenti ed elementi HTML.</span><span class="sxs-lookup"><span data-stu-id="8806b-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="8806b-110">Per la procedura è necessario saper eseguire le attività di base in Windows Forms, ad esempio la creazione di un nuovo progetto e l'aggiunta di un controllo a un modulo.</span><span class="sxs-lookup"><span data-stu-id="8806b-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>

### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="8806b-111">Per elaborare le modifiche di stile in un Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="8806b-111">To process style changes in a Windows Forms application</span></span>

1. <span data-ttu-id="8806b-112">Creare un nuovo progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8806b-112">Create a new Windows Forms project.</span></span>

2. <span data-ttu-id="8806b-113">Creare un nuovo file di classe che termina con l'estensione appropriata per il linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8806b-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>

3. <span data-ttu-id="8806b-114">Copiare il `StyleGenerator` codice della classe nella sezione esempio di questo argomento nel file di classe e salvare il codice.</span><span class="sxs-lookup"><span data-stu-id="8806b-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>

4. <span data-ttu-id="8806b-115">Salvare il codice HTML seguente in un file denominato Test.htm.</span><span class="sxs-lookup"><span data-stu-id="8806b-115">Save the following HTML to a file named Test.htm.</span></span>

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

5. <span data-ttu-id="8806b-116">Aggiungere un <xref:System.Windows.Forms.WebBrowser> controllo denominato `webBrowser1` al form principale del progetto.</span><span class="sxs-lookup"><span data-stu-id="8806b-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>

6. <span data-ttu-id="8806b-117">Aggiungere il codice seguente al file di codice del progetto.</span><span class="sxs-lookup"><span data-stu-id="8806b-117">Add the following code to your project's code file.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8806b-118">Verificare che il `webBrowser1_DocumentCompleted` gestore eventi sia configurato come listener per l' <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="8806b-118">Ensure that the `webBrowser1_DocumentCompleted` event handler is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="8806b-119">In Visual Studio fare doppio clic sul <xref:System.Windows.Forms.WebBrowser> controllo; in un editor di testo, configurare il listener a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="8806b-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. <span data-ttu-id="8806b-120">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="8806b-120">Run the project.</span></span> <span data-ttu-id="8806b-121">Eseguire il cursore sul primo `DIV` per osservare gli effetti del codice.</span><span class="sxs-lookup"><span data-stu-id="8806b-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>

## <a name="example"></a><span data-ttu-id="8806b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="8806b-122">Example</span></span>

<span data-ttu-id="8806b-123">Nell'esempio di codice seguente viene illustrato il codice completo per la `StyleGenerator` classe, che analizza un valore di stile esistente, supporta l'aggiunta, la modifica e la rimozione di stili e restituisce un nuovo valore di stile con le modifiche richieste.</span><span class="sxs-lookup"><span data-stu-id="8806b-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8806b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8806b-124">See also</span></span>

- <xref:System.Windows.Forms.HtmlElement>
