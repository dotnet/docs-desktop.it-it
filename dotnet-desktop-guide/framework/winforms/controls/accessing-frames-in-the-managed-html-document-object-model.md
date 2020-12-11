---
title: Accesso a frame nel Document Object Model HTML gestito
ms.date: 03/30/2017
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
ms.openlocfilehash: 5a9864184e92c3c6bbcf6a613fd1092238181a93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952703"
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a>Accesso a frame nel Document Object Model HTML gestito
Alcuni documenti HTML sono composti da *frame* o finestre che possono conservare i propri documenti HTML distinti. Con i frame è possibile creare facilmente pagine HTML in cui una o più parti della pagina sono statiche, ad esempio una barra di spostamento, mentre il contenuto degli altri frame cambia continuamente.  
  
 Gli autori di documenti HTML possono creare i frame in uno dei due modi seguenti:  
  
- Usando i tag `FRAMESET` e `FRAME`, che creano finestre fisse.  
  
 -oppure-  
  
- Usando il tag `IFRAME`, che crea una finestra mobile che può essere riposizionata in fase di esecuzione.  
  
1. Poiché i frame contengono documenti HTML, vengono rappresentati in Document Object Model (DOM) sia come elementi finestra che come elementi frame.  
  
2. Quando si accede a un tag `FRAME` o `IFRAME` usando la raccolta Frames di <xref:System.Windows.Forms.HtmlWindow>, si recupererà l'elemento finestra corrispondente al frame. Questo rappresenta tutte le proprietà dinamiche del frame, ad esempio l'URL, il documento e le dimensioni correnti.  
  
3. Quando si accede a un tag `FRAME` o `IFRAME` usando la proprietà <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> di <xref:System.Windows.Forms.HtmlWindow>, la raccolta <xref:System.Windows.Forms.HtmlElement.Children%2A> oppure metodi come <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> o <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, si recupererà l'elemento frame. Questo rappresenta le proprietà statiche del frame, incluso l'URL specificato nel file HTML originale.  
  
## <a name="frames-and-security"></a>Frame e sicurezza  
 L'accesso ai frame è complicato dal fatto che il DOM HTML gestito implementa una misura di sicurezza nota come *sicurezza di scripting tra frame*. Se un documento contiene un `FRAMESET` con due o più `FRAME` in domini diversi, questi `FRAME` non possono interagire tra loro. In altre parole, un `FRAME` che Visualizza il contenuto del sito Web non è in grado di accedere alle informazioni in un `FRAME` che ospita un sito di terze parti, ad esempio `http://www.adatum.com/` . Questa misura di sicurezza è implementata a livello della classe <xref:System.Windows.Forms.HtmlWindow>. È possibile ottenere informazioni generali su un `FRAME` che ospita un altro sito Web, ad esempio l'URL, ma non si potrà accedere alla proprietà <xref:System.Windows.Forms.HtmlWindow.Document%2A> o modificare le dimensioni o la posizione del `FRAME` o dell'`IFRAME` di hosting.  
  
 Questa regola si applica anche alle finestre aperte con i metodi <xref:System.Windows.Forms.HtmlWindow.Open%2A> e <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A>. Se la finestra aperta è in un dominio diverso da quello della pagina ospitata nel controllo <xref:System.Windows.Forms.WebBrowser>, non sarà possibile spostare la finestra o esaminarne i contenuti. Queste restrizioni vengono applicate anche se si usa il controllo <xref:System.Windows.Forms.WebBrowser> per visualizzare un sito Web diverso dal sito Web usato per distribuire l'applicazione basata su Windows Form. Se si utilizza la tecnologia di distribuzione ClickOnce per installare l'applicazione dal sito Web A e si utilizza <xref:System.Windows.Forms.WebBrowser> per visualizzare il sito Web b, non sarà possibile accedere ai dati del sito Web b.  
  
## <a name="see-also"></a>Vedere anche

- [\<frame> elemento](https://developer.mozilla.org/docs/Web/HTML/Element/frame)
- [Utilizzare il Document Object Model HTML gestito](using-the-managed-html-document-object-model.md)
