---
title: Sicurezza dei controlli WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 3412a775cd62723bb1d7ab8548b8a89ea05ad7f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964654"
---
# <a name="webbrowser-security"></a>Sicurezza dei controlli WebBrowser

Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare solo con attendibilità totale. Il contenuto HTML visualizzato nel controllo può provenire da server Web esterni e può contenere codice non gestito sotto forma di script o controlli Web. Se si utilizza il <xref:System.Windows.Forms.WebBrowser> controllo in questa situazione, il controllo non è meno sicuro di Internet Explorer, ma il <xref:System.Windows.Forms.WebBrowser> controllo gestito non impedisce l'esecuzione di tale codice non gestito.  
  
 Per ulteriori informazioni sui problemi di sicurezza relativi al controllo ActiveX sottostante `WebBrowser` , vedere [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- [Cenni preliminari sul controllo WebBrowser](webbrowser-control-overview.md)
- [Controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
