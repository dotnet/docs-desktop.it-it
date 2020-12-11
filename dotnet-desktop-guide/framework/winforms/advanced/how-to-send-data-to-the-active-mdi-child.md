---
title: 'Procedura: Inviare dati al figlio MDI attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963289"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Procedura: Inviare dati al figlio MDI attivo
Spesso, all'interno del contesto di [applicazioni con interfaccia a documenti multipli (MDI)](multiple-document-interface-mdi-applications.md), sarà necessario inviare dati alla finestra figlio attiva, ad esempio quando l'utente incolla i dati dagli Appunti in un'applicazione MDI.  
  
> [!NOTE]
> Per informazioni sulla verifica della finestra figlio con lo stato attivo e sull'invio del contenuto agli Appunti, vedere [determinazione del figlio MDI attivo](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Per inviare i dati alla finestra figlio MDI attiva dagli Appunti  
  
1. All'interno di un metodo, copiare il testo negli Appunti nel controllo attivo del form figlio attivo.  
  
    > [!NOTE]
    > In questo esempio si presuppone che esista un form padre MDI ( `Form1` ) con una o più finestre figlio MDI contenenti un <xref:System.Windows.Forms.RichTextBox> controllo. Per ulteriori informazioni, vedere [creazione di form padre MDI](how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();
                }  
             }  
          }  
          catch
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](multiple-document-interface-mdi-applications.md)
- [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](how-to-create-mdi-child-forms.md)
- [Procedura: Determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)
- [Procedura: Disporre form figlio MDI](how-to-arrange-mdi-child-forms.md)
