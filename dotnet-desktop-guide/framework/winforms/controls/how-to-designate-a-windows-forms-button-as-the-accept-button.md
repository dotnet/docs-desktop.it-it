---
title: Designare un pulsante come pulsante accetta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961906"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="a0bc0-102">Procedura: Designare un pulsante Windows Forms come pulsante di conferma</span><span class="sxs-lookup"><span data-stu-id="a0bc0-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="a0bc0-103">In qualsiasi Windows Form è possibile designare un <xref:System.Windows.Forms.Button> controllo come pulsante di accettazione, noto anche come pulsante predefinito.</span><span class="sxs-lookup"><span data-stu-id="a0bc0-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="a0bc0-104">Ogni volta che l'utente preme il tasto invio, viene fatto clic sul pulsante predefinito, indipendentemente da quale altro controllo nel form abbia lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a0bc0-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0bc0-105">Le eccezioni a questo si verificano quando il controllo con lo stato attivo è un altro pulsante, in tal caso verrà fatto clic sul pulsante con lo stato attivo o su una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="a0bc0-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="a0bc0-106">Per impostare il pulsante accetta</span><span class="sxs-lookup"><span data-stu-id="a0bc0-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="a0bc0-107">Impostare la proprietà del form sul <xref:System.Windows.Forms.Form.AcceptButton%2A> controllo appropriato <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="a0bc0-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0bc0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0bc0-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="a0bc0-109">Panoramica del controllo Button</span><span class="sxs-lookup"><span data-stu-id="a0bc0-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="a0bc0-110">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0bc0-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="a0bc0-111">Procedura: rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0bc0-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="a0bc0-112">Procedura: Designare un pulsante Windows Forms come pulsante di annullamento</span><span class="sxs-lookup"><span data-stu-id="a0bc0-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="a0bc0-113">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="a0bc0-113">Button Control</span></span>](button-control-windows-forms.md)
