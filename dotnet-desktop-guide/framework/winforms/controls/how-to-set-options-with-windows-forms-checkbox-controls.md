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
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedura: impostare opzioni con i controlli CheckBox di Windows Form
Un <xref:System.Windows.Forms.CheckBox> controllo Windows Forms viene usato per fornire agli utenti le opzioni true/false o Yes/No. Il controllo Visualizza un segno di spunta quando viene selezionato.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Per impostare le opzioni con i controlli CheckBox  
  
1. Esaminare il valore della <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinarne lo stato e utilizzare tale valore per impostare un'opzione.  
  
     Nell'esempio di codice riportato di seguito, quando <xref:System.Windows.Forms.CheckBox> <xref:System.Windows.Forms.CheckBox.CheckedChanged> viene generato l'evento del controllo, la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà del form viene impostata su `false` se la casella di controllo è selezionata. Questa operazione è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.CheckBox>
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: rispondere alla selezione di controlli CheckBox Windows Form](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (controllo)](checkbox-control-windows-forms.md)
