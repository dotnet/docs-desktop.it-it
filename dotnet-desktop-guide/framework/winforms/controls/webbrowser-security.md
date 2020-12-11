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
# <a name="webbrowser-security"></a><span data-ttu-id="518c6-102">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="518c6-102">WebBrowser Security</span></span>

<span data-ttu-id="518c6-103">Il <xref:System.Windows.Forms.WebBrowser> controllo è progettato per funzionare solo con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="518c6-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="518c6-104">Il contenuto HTML visualizzato nel controllo può provenire da server Web esterni e può contenere codice non gestito sotto forma di script o controlli Web.</span><span class="sxs-lookup"><span data-stu-id="518c6-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="518c6-105">Se si utilizza il <xref:System.Windows.Forms.WebBrowser> controllo in questa situazione, il controllo non è meno sicuro di Internet Explorer, ma il <xref:System.Windows.Forms.WebBrowser> controllo gestito non impedisce l'esecuzione di tale codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="518c6-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="518c6-106">Per ulteriori informazioni sui problemi di sicurezza relativi al controllo ActiveX sottostante `WebBrowser` , vedere [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="518c6-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518c6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518c6-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="518c6-108">Cenni preliminari sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="518c6-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="518c6-109">[Controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="518c6-109">[WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
