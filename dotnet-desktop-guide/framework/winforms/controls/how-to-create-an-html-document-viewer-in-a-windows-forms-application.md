---
title: Creare un visualizzatore di documenti HTML in un'app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963907"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="ecb20-102">Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="ecb20-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="ecb20-103">È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per visualizzare e stampare documenti HTML senza fornire le funzionalità complete di un Web browser Internet.</span><span class="sxs-lookup"><span data-stu-id="ecb20-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="ecb20-104">Questa opzione è utile quando si desidera sfruttare le funzionalità di formattazione di HTML, ma non si desidera che gli utenti carichino pagine Web arbitrarie che possono contenere controlli Web non attendibili o codice di script potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="ecb20-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="ecb20-105">È possibile limitare la funzionalità del <xref:System.Windows.Forms.WebBrowser> controllo in questo modo, ad esempio, per usarlo come visualizzatore di posta elettronica HTML o per fornire la Guida in formato HTML nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ecb20-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="ecb20-106">Per creare un visualizzatore di documenti HTML</span><span class="sxs-lookup"><span data-stu-id="ecb20-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="ecb20-107">Impostare la <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> proprietà su `false` per impedire <xref:System.Windows.Forms.WebBrowser> che il controllo apra i file rilasciati su di esso.</span><span class="sxs-lookup"><span data-stu-id="ecb20-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="ecb20-108">Impostare la <xref:System.Windows.Forms.WebBrowser.Url%2A> proprietà sul percorso del file iniziale da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ecb20-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ecb20-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ecb20-109">Compiling the Code</span></span>  
 <span data-ttu-id="ecb20-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecb20-110">This example requires:</span></span>  
  
- <span data-ttu-id="ecb20-111">Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="ecb20-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="ecb20-112">Riferimenti agli assembly `System` e `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="ecb20-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb20-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecb20-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="ecb20-114">Cenni preliminari sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="ecb20-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="ecb20-115">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="ecb20-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="ecb20-116">Procedura: Passare a un URL con il controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="ecb20-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="ecb20-117">Procedura: Stampare con un controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="ecb20-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
