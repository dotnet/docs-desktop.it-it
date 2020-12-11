---
title: 'Procedura: Accedere al Document Object Model HTML gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 42f2f4d7a518daa6341809974b10978bec99f1a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962143"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a>Procedura: Accedere al Document Object Model HTML gestito

È possibile accedere a Document Object Model (DOM) HTML gestito da due tipi di applicazione:  
  
- Un'applicazione Windows Form (con estensione EXE) che ha ospitato il controllo gestito <xref:System.Windows.Forms.WebBrowser>. Queste due tecnologie sono complementari: il controllo <xref:System.Windows.Forms.WebBrowser> visualizza la pagina all'utente e DOM HTML rappresenta la struttura logica del documento.  
  
- Una classe <xref:System.Windows.Forms.UserControl> Windows Form ospitata in Internet Explorer. Si può accedere a DOM HTML che rappresenta la pagina in cui è ospitata la classe <xref:System.Windows.Forms.UserControl> per modificare la struttura del documento o aprire finestre di dialogo modali, tra le molte altre possibilità.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Per accedere a DOM da un'applicazione Windows Forms  
  
1. Ospitare un controllo <xref:System.Windows.Forms.WebBrowser> nell'applicazione Windows Form e verificare la presenza dell'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>. Per altre informazioni su come ospitare i controlli e verificare gli eventi, vedere [Eventi](/dotnet/standard/events/index).  
  
2. Recuperare la classe <xref:System.Windows.Forms.HtmlDocument> per la pagina corrente accedendo alla proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> del controllo <xref:System.Windows.Forms.WebBrowser>.  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Per accedere a DOM da una classe UserControl ospitata in Internet Explorer  
  
1. Creare una classe personalizzata derivata dalla classe <xref:System.Windows.Forms.UserControl>. Per altre informazioni, vedere [Procedura: Modificare controlli compositi](how-to-author-composite-controls.md).  
  
2. Inserire il codice seguente nel gestore eventi Load per la classe <xref:System.Windows.Forms.UserControl> personalizzata:  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
1. Quando si usa DOM tramite il controllo <xref:System.Windows.Forms.WebBrowser>, è consigliabile attendere sempre finché si verifica l'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> prima di provare ad accedere alla proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> del controllo <xref:System.Windows.Forms.WebBrowser>. L'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> viene generato dopo il caricamento dell'intero documento. Se si usa DOM prima che l'evento sia generato, si rischia di causare un'eccezione di runtime.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
  
1. L'applicazione o la classe <xref:System.Windows.Forms.UserControl> richiederà l'attendibilità totale per accedere a DOM HTML gestito. Se si distribuisce una Windows Forms Application usando ClickOnce, è possibile richiedere l'attendibilità totale usando l'elevazione delle autorizzazioni o la distribuzione di applicazioni attendibili. per informazioni dettagliate, vedere [protezione delle applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications) .  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzare il Document Object Model HTML gestito](using-the-managed-html-document-object-model.md)
