---
title: Visualizza l'anteprima di stampa nelle app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 7737cd06001f9acfde5eb44fdff9aaa880f23e79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961855"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms
È possibile utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo per consentire agli utenti di visualizzare un documento, spesso prima che sia stampato.  
  
 A tale scopo, è necessario specificare un'istanza della <xref:System.Drawing.Printing.PrintDocument> classe. si tratta del documento da stampare. Per altre informazioni sull'uso dell'anteprima di stampa con il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare in Windows Forms usando l'anteprima di stampa](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
> Per utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo in fase di esecuzione, è necessario che gli utenti dispongano di una stampante installata sul proprio computer, localmente o tramite una rete, in quanto si tratta in parte del modo in <xref:System.Windows.Forms.PrintPreviewDialog> cui il componente determina il modo in cui un documento viene stampato.  
  
 Il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Usa la <xref:System.Drawing.Printing.PrinterSettings> classe. Inoltre, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Usa la <xref:System.Drawing.Printing.PageSettings> classe, proprio come il <xref:System.Windows.Forms.PrintPreviewDialog> componente. Il documento di stampa specificato nella <xref:System.Windows.Forms.PrintPreviewDialog> proprietà del controllo <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> si riferisce alle istanze <xref:System.Drawing.Printing.PrinterSettings> delle <xref:System.Drawing.Printing.PageSettings> classi e e vengono usate per eseguire il rendering del documento nella finestra di anteprima.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Per visualizzare le pagine utilizzando il controllo PrintPreviewDialog  
  
- Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.  
  
     Nell'esempio di codice seguente il <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> gestore eventi del controllo apre un'istanza del <xref:System.Windows.Forms.PrintPreviewDialog> controllo. Il documento di stampa è specificato nella <xref:System.Windows.Forms.PrintDialog.Document%2A> Proprietà. Nell'esempio seguente non viene specificato alcun documento di stampa.  
  
     Per l'esempio è necessario che il form contenga un <xref:System.Windows.Forms.Button> controllo, un <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument` e un <xref:System.Windows.Forms.PrintPreviewDialog> controllo.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Componente PrintDocument](printdocument-component-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Supporto per la stampa in Windows Form](../advanced/windows-forms-print-support.md)
- [WinForms](../index.yml)
