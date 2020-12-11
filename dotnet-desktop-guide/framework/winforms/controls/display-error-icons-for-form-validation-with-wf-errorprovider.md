---
title: Visualizza le icone di errore per la convalida dei form con il componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950955"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms
È possibile utilizzare un <xref:System.Windows.Forms.ErrorProvider> componente Windows Forms per visualizzare un'icona di errore quando l'utente immette dati non validi. È necessario disporre di almeno due controlli sul form per eseguire una tabulazione tra di essi e richiamare quindi il codice di convalida.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Per visualizzare un'icona di errore quando il valore di un controllo non è valido  
  
1. Aggiungere due controlli, ad esempio caselle di testo, a un Windows Form.  
  
2. Aggiungere un <xref:System.Windows.Forms.ErrorProvider> componente al form.  
  
3. Selezionare il primo controllo e aggiungere il codice al <xref:System.Windows.Forms.Control.Validating> gestore dell'evento. Affinché il codice venga eseguito correttamente, è necessario che la procedura sia connessa all'evento. Per altre informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Il codice seguente verifica la validità dei dati immessi dall'utente. Se i dati non sono validi, <xref:System.Windows.Forms.ErrorProvider.SetError%2A> viene chiamato il metodo. Il primo argomento del <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo specifica il controllo a cui visualizzare l'icona accanto a. Il secondo argomento è il testo dell'errore da visualizzare.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Eseguire il progetto. Digitare non valido (in questo esempio, dati non numerici) nel primo controllo, quindi premere TAB per la seconda. Quando viene visualizzata l'icona di errore, puntare con il puntatore del mouse per visualizzare il testo dell'errore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Panoramica del componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
