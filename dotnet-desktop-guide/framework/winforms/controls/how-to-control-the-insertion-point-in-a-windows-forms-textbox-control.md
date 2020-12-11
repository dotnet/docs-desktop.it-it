---
title: Controllare il punto di inserimento nel controllo TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963943"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms
Quando un <xref:System.Windows.Forms.TextBox> controllo Windows Forms riceve lo stato attivo per la prima volta, l'inserimento predefinito all'interno della casella di testo si trova a sinistra di qualsiasi testo esistente. L'utente può spostare il punto di inserimento con la tastiera o con il mouse. Se la casella di testo perde e quindi riacquisisce lo stato attivo, il punto di inserimento sarà ogni volta che l'utente lo posiziona.  
  
 In alcuni casi, questo comportamento può essere sconcertante per l'utente. In un'applicazione di elaborazione di testo, l'utente potrebbe aspettarsi che vengano visualizzati nuovi caratteri dopo un testo esistente. In un'applicazione di immissione dati, l'utente può prevedere che i nuovi caratteri sostituiscano qualsiasi voce esistente. Le <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà e consentono di modificare il comportamento in base allo scopo.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Per controllare il punto di inserimento in un controllo TextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> su un valore appropriato. Zero posiziona il punto di inserimento immediatamente a sinistra del primo carattere.  
  
2. Opzionale Impostare la <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà sulla lunghezza del testo che si desidera selezionare.  
  
     Il codice seguente restituisce sempre il punto di inserimento a 0. Il `TextBox1_Enter` gestore eventi deve essere associato al controllo. per ulteriori informazioni, vedere [creazione di gestori eventi in Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>Rendere visibile il punto di inserimento per impostazione predefinita  
 Il <xref:System.Windows.Forms.TextBox> punto di inserimento è visibile per impostazione predefinita in un nuovo form solo se il <xref:System.Windows.Forms.TextBox> controllo è il primo nell'ordine di tabulazione. In caso contrario, il punto di inserimento viene visualizzato solo se si assegna lo <xref:System.Windows.Forms.TextBox> stato attivo con la tastiera o con il mouse.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Per rendere visibile il punto di inserimento della casella di testo per impostazione predefinita in un nuovo form  
  
- Impostare la <xref:System.Windows.Forms.TextBox> proprietà del controllo <xref:System.Windows.Forms.Control.TabIndex%2A> su `0` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Panoramica del controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox di Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
