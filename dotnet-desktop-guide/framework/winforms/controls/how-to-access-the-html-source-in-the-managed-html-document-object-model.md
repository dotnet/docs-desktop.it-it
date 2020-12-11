---
title: "Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 2db3e5a16268d71d972a84d65b3f0aa37771923c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962845"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="daab7-102">Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="daab7-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="daab7-103">Le proprietà <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> r <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo <xref:System.Windows.Forms.WebBrowser> restituiscono l'HTML del documento corrente come si presentava al momento della visualizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="daab7-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="daab7-104">Se tuttavia si modifica la pagina con chiamate a metodo e proprietà, ad esempio <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> e <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, queste modifiche non saranno visualizzate quando si chiama <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> e <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span><span class="sxs-lookup"><span data-stu-id="daab7-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="daab7-105">Per ottenere l'origine HTML più recente del DOM, è necessario chiamare la proprietà <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> sull'elemento HTML.</span><span class="sxs-lookup"><span data-stu-id="daab7-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="daab7-106">La procedura seguente mostra come recuperare l'origine dinamica e visualizzarla in un menu di scelta rapida separato.</span><span class="sxs-lookup"><span data-stu-id="daab7-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="daab7-107">Recupero dell'origine dinamica con la proprietà OuterHtml</span><span class="sxs-lookup"><span data-stu-id="daab7-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1. <span data-ttu-id="daab7-108">Creare una nuova applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="daab7-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="daab7-109">Iniziare con un singolo <xref:System.Windows.Forms.Form> e chiamarlo `Form1` .</span><span class="sxs-lookup"><span data-stu-id="daab7-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2. <span data-ttu-id="daab7-110">Ospitare il <xref:System.Windows.Forms.WebBrowser> controllo nel Windows Forms Application e denominarlo `WebBrowser1` .</span><span class="sxs-lookup"><span data-stu-id="daab7-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="daab7-111">Per altre informazioni, vedere [procedura: aggiungere funzionalità del browser Web a un'applicazione Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="daab7-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3. <span data-ttu-id="daab7-112">Creare un secondo <xref:System.Windows.Forms.Form> nell'applicazione denominata `CodeForm` .</span><span class="sxs-lookup"><span data-stu-id="daab7-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4. <span data-ttu-id="daab7-113">Aggiungere un <xref:System.Windows.Forms.RichTextBox> controllo a `CodeForm` e impostare la relativa <xref:System.Windows.Forms.Control.Dock%2A> proprietà su `Fill` .</span><span class="sxs-lookup"><span data-stu-id="daab7-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5. <span data-ttu-id="daab7-114">Creare una proprietà pubblica su `CodeForm` chiamata `Code` .</span><span class="sxs-lookup"><span data-stu-id="daab7-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6. <span data-ttu-id="daab7-115">Aggiungere un <xref:System.Windows.Forms.Button> controllo denominato `Button1` a <xref:System.Windows.Forms.Form> e monitorare l' <xref:System.Windows.Forms.Control.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="daab7-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="daab7-116">Per informazioni dettagliate sugli eventi di monitoraggio, vedere [eventi](/dotnet/standard/events/index).</span><span class="sxs-lookup"><span data-stu-id="daab7-116">For details on monitoring events, see [Events](/dotnet/standard/events/index).</span></span>  
  
7. <span data-ttu-id="daab7-117">Aggiungere il codice seguente al gestore eventi <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="daab7-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="daab7-118">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="daab7-118">Robust Programming</span></span>  

 <span data-ttu-id="daab7-119">Verificare sempre il valore di <xref:System.Windows.Forms.WebBrowser.Document%2A> prima di tentarne il recupero.</span><span class="sxs-lookup"><span data-stu-id="daab7-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="daab7-120">Se il caricamento della pagina corrente non viene completato, è possibile che l'inizializzazione di <xref:System.Windows.Forms.WebBrowser.Document%2A> o di uno o più dei relativi oggetti figlio non sia eseguita.</span><span class="sxs-lookup"><span data-stu-id="daab7-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daab7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daab7-121">See also</span></span>

- [<span data-ttu-id="daab7-122">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="daab7-122">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
- [<span data-ttu-id="daab7-123">Cenni preliminari sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="daab7-123">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
