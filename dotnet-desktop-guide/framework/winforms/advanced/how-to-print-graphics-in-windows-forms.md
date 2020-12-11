---
title: 'Procedura: stampare grafica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963322"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Procedura: Stampare grafica in Windows Form
Spesso è necessario stampare elementi grafici nell'applicazione basata su Windows. La <xref:System.Drawing.Graphics> classe fornisce i metodi per disegnare oggetti in un dispositivo, ad esempio una schermata o una stampante.  
  
### <a name="to-print-graphics"></a>Per stampare grafica  
  
1. Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.  
  
2. Nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi usare la <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe per indicare alla stampante il tipo di grafica da stampare.  
  
     Nell'esempio di codice riportato di seguito viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione. Il rettangolo presenta il percorso e le dimensioni seguenti: a partire da 100, 150 con larghezza 250 e altezza 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Supporto per la stampa in Windows Form](windows-forms-print-support.md)
