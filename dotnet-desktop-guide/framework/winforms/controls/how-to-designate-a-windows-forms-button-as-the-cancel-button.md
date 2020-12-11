---
title: Designare un pulsante come pulsante Annulla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963844"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="f89e5-102">Procedura: Designare un pulsante Windows Forms come pulsante di annullamento</span><span class="sxs-lookup"><span data-stu-id="f89e5-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="f89e5-103">In qualsiasi Windows Form è possibile designare un <xref:System.Windows.Forms.Button> controllo come pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="f89e5-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="f89e5-104">Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="f89e5-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="f89e5-105">Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f89e5-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="f89e5-106">Per impostare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="f89e5-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="f89e5-107">Impostare la proprietà del form sul <xref:System.Windows.Forms.Form.CancelButton%2A> controllo appropriato <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="f89e5-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f89e5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f89e5-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="f89e5-109">Panoramica del controllo Button</span><span class="sxs-lookup"><span data-stu-id="f89e5-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="f89e5-110">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="f89e5-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="f89e5-111">Procedura: rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f89e5-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="f89e5-112">Procedura: Designare un pulsante Windows Forms come pulsante di conferma</span><span class="sxs-lookup"><span data-stu-id="f89e5-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="f89e5-113">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="f89e5-113">Button Control</span></span>](button-control-windows-forms.md)
