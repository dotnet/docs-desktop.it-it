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
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application
È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per visualizzare e stampare documenti HTML senza fornire le funzionalità complete di un Web browser Internet. Questa opzione è utile quando si desidera sfruttare le funzionalità di formattazione di HTML, ma non si desidera che gli utenti carichino pagine Web arbitrarie che possono contenere controlli Web non attendibili o codice di script potenzialmente dannoso. È possibile limitare la funzionalità del <xref:System.Windows.Forms.WebBrowser> controllo in questo modo, ad esempio, per usarlo come visualizzatore di posta elettronica HTML o per fornire la Guida in formato HTML nell'applicazione.  
  
### <a name="to-create-an-html-document-viewer"></a>Per creare un visualizzatore di documenti HTML  
  
1. Impostare la <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> proprietà su `false` per impedire <xref:System.Windows.Forms.WebBrowser> che il controllo apra i file rilasciati su di esso.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. Impostare la <xref:System.Windows.Forms.WebBrowser.Url%2A> proprietà sul percorso del file iniziale da visualizzare.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.  
  
- Riferimenti agli assembly `System` e `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [Cenni preliminari sul controllo WebBrowser](webbrowser-control-overview.md)
- [Sicurezza dei controlli WebBrowser](webbrowser-security.md)
- [Procedura: Passare a un URL con il controllo WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedura: Stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
