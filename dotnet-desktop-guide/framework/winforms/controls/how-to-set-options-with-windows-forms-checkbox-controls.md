---
title: Impostare le opzioni con i controlli CheckBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961636"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="32f12-102">Procedura: impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="32f12-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="32f12-103">Un <xref:System.Windows.Forms.CheckBox> controllo Windows Forms viene usato per fornire agli utenti le opzioni true/false o Yes/No.</span><span class="sxs-lookup"><span data-stu-id="32f12-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="32f12-104">Il controllo Visualizza un segno di spunta quando viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="32f12-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="32f12-105">Per impostare le opzioni con i controlli CheckBox</span><span class="sxs-lookup"><span data-stu-id="32f12-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="32f12-106">Esaminare il valore della <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinarne lo stato e utilizzare tale valore per impostare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="32f12-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="32f12-107">Nell'esempio di codice riportato di seguito, quando <xref:System.Windows.Forms.CheckBox> <xref:System.Windows.Forms.CheckBox.CheckedChanged> viene generato l'evento del controllo, la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà del form viene impostata su `false` se la casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="32f12-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="32f12-108">Questa operazione è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32f12-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="32f12-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32f12-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="32f12-110">Panoramica del controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="32f12-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="32f12-111">Procedura: rispondere alla selezione di controlli CheckBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="32f12-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="32f12-112">CheckBox (controllo)</span><span class="sxs-lookup"><span data-stu-id="32f12-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
