---
title: Completa processi di stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952433"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Procedura: Completare processi di stampa in Windows Form
Spesso, i processori di Word e le altre applicazioni che coinvolgono la stampa offrono la possibilità di visualizzare un messaggio agli utenti per completare un processo di stampa. È possibile fornire questa funzionalità nel Windows Forms gestendo l' <xref:System.Drawing.Printing.PrintDocument.EndPrint> evento del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 Per la procedura seguente è necessario aver creato un'applicazione basata su Windows con un <xref:System.Drawing.Printing.PrintDocument> componente, che rappresenta il modo standard per abilitare la stampa da un'applicazione basata su Windows. Per altre informazioni sulla stampa da Windows Forms usando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: creare processi di stampa standard Windows Forms](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Per completare un processo di stampa  
  
1. Impostare la <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     Nell'esempio di codice seguente viene visualizzata una finestra di messaggio che indica che il documento ha terminato la stampa.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
