---
title: 'Procedura dettagliata: Uso del controllo MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964666"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Procedura dettagliata: Uso del controllo MaskedTextBox
Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Inizializzazione del <xref:System.Windows.Forms.MaskedTextBox> controllo  
  
- Uso del <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> gestore eventi per avvertire l'utente quando un carattere non è conforme alla maschera  
  
- Assegnazione di un tipo alla <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà e utilizzo del <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> gestore eventi per avvertire l'utente quando il valore di cui si sta tentando di eseguire il commit non è valido per il tipo  
  
## <a name="creating-the-project-and-adding-a-control"></a>Creazione del progetto e aggiunta di un controllo  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Per aggiungere un controllo MaskedTextBox al form  
  
1. Aprire il modulo in cui si desidera inserire il <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
2. Trascinare un <xref:System.Windows.Forms.MaskedTextBox> controllo dalla **casella degli strumenti** nel form.  
  
3. Fare clic con il pulsante destro del mouse sul controllo e scegliere **Proprietà**. Nella finestra **Proprietà** selezionare la proprietà **mask** e fare clic sul pulsante **...** (puntini di sospensione) accanto al nome della proprietà.  
  
4. Nella finestra di dialogo **maschera di input** selezionare la maschera **data breve** e fare clic su **OK**.  
  
5. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> proprietà su `true` . Questa proprietà genera un breve segnale acustico al suono ogni volta che l'utente tenta di immettere un carattere che viola la definizione della maschera.  
  
 Per un riepilogo dei caratteri supportati dalla proprietà Mask, vedere la sezione Osservazioni della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Proprietà.  
  
## <a name="alert-the-user-to-input-errors"></a>Avvisare l'utente di inserire errori  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Aggiungere un fumetto suggerimento per l'input della maschera rifiutata  
  
1. Tornare alla **casella degli strumenti** e aggiungere un <xref:System.Windows.Forms.ToolTip> al form.  
  
2. Creare un gestore eventi per l' <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> evento che genera <xref:System.Windows.Forms.ToolTip> quando si verifica un errore di input. Il fumetto suggerimento rimane visibile per cinque secondi o fino a quando l'utente non fa clic su di esso.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Avvisa l'utente di un tipo non valido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Aggiungere un fumetto suggerimento per i tipi di dati non validi  
  
1. Nel <xref:System.Windows.Forms.Form.Load> gestore eventi del form assegnare un <xref:System.Type> oggetto che rappresenta il <xref:System.DateTime> tipo alla proprietà del <xref:System.Windows.Forms.MaskedTextBox> controllo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> :  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. Aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MaskedTextBox>
- [Controllo MaskedTextBox](maskedtextbox-control-windows-forms.md)
