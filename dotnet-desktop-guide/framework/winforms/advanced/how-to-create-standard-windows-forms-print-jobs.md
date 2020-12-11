---
title: Creare processi di stampa standard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960658"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedura: Creare processi di stampa standard per Windows Form
Il fondamento della stampa in Windows Forms è il <xref:System.Drawing.Printing.PrintDocument> componente, più specificamente l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento. Scrivendo il codice per gestire l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, è possibile specificare gli elementi da stampare e la relativa modalità di stampa.  
  
### <a name="to-create-a-print-job"></a>Per creare un processo di stampa  
  
1. Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Dovrai scrivere codice per la tua logica di stampa. Inoltre, sarà necessario specificare il materiale da stampare.  
  
     Nell'esempio di codice seguente viene creato un elemento grafico di esempio nella forma di un rettangolo rosso nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi per agire come materiale da stampare.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     È anche possibile scrivere il codice per gli <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventi e <xref:System.Drawing.Printing.PrintDocument.EndPrint> , includendo ad esempio un Integer che rappresenta il numero totale di pagine da stampare che viene decrementato Man mano che ogni pagina viene stampata.  
  
    > [!NOTE]
    > È possibile aggiungere un <xref:System.Windows.Forms.PrintDialog> componente al form per fornire agli utenti un'interfaccia utente pulita ed efficiente. L'impostazione della <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> componente consente di impostare le proprietà correlate al documento di stampa che si sta utilizzando nel form. Per ulteriori informazioni sul <xref:System.Windows.Forms.PrintDialog> componente, vedere [componente PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Per ulteriori informazioni sulle specifiche di Windows Forms processi di stampa, inclusa la modalità di creazione di un processo di stampa a livello di codice, vedere <xref:System.Drawing.Printing.PrintPageEventArgs> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
