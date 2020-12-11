---
title: 'Procedura: Visualizzare un elenco di tipi di carattere con il componente FontDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 05e9b5e1280d0318354b0d47f4d78f7ec1c5f4e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965167"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Procedura: Visualizzare un elenco di tipi di carattere con il componente FontDialog
Il componente [FontDialog](fontdialog-component-windows-forms.md) consente agli utenti di selezionare un tipo di carattere, nonché di modificarne gli aspetti di visualizzazione, ad esempio il peso e le dimensioni.  
  
 Il tipo di carattere selezionato nella finestra di dialogo viene restituito nella <xref:System.Windows.Forms.FontDialog.Font%2A> Proprietà. Pertanto, l'utilizzo del tipo di carattere selezionato dall'utente è semplice quanto la lettura di una proprietà.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Per selezionare le proprietà del tipo di carattere utilizzando il componente FontDialog  
  
1. Consente di visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
2. Utilizzare la <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità di chiusura della finestra di dialogo.  
  
3. Utilizzare la <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà per impostare il tipo di carattere desiderato.  
  
     Nell'esempio seguente il <xref:System.Windows.Forms.Button> gestore eventi del controllo <xref:System.Windows.Forms.Control.Click> apre un <xref:System.Windows.Forms.FontDialog> componente. Quando si sceglie un tipo di carattere e l'utente fa clic su **OK**, la <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà di un <xref:System.Windows.Forms.TextBox> controllo che si trova nel form viene impostata sul tipo di carattere scelto. Nell'esempio si presuppone che il form disponga di un <xref:System.Windows.Forms.Button> controllo, di un  <xref:System.Windows.Forms.TextBox> controllo e di un <xref:System.Windows.Forms.FontDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FontDialog>
- [Componente FontDialog](fontdialog-component-windows-forms.md)
