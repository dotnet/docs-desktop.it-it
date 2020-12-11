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
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="bf038-102">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="bf038-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="bf038-103">Spesso è necessario stampare elementi grafici nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="bf038-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="bf038-104">La <xref:System.Drawing.Graphics> classe fornisce i metodi per disegnare oggetti in un dispositivo, ad esempio una schermata o una stampante.</span><span class="sxs-lookup"><span data-stu-id="bf038-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="bf038-105">Per stampare grafica</span><span class="sxs-lookup"><span data-stu-id="bf038-105">To print graphics</span></span>  
  
1. <span data-ttu-id="bf038-106">Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.</span><span class="sxs-lookup"><span data-stu-id="bf038-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="bf038-107">Nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi usare la <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe per indicare alla stampante il tipo di grafica da stampare.</span><span class="sxs-lookup"><span data-stu-id="bf038-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="bf038-108">Nell'esempio di codice riportato di seguito viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="bf038-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="bf038-109">Il rettangolo presenta il percorso e le dimensioni seguenti: a partire da 100, 150 con larghezza 250 e altezza 250.</span><span class="sxs-lookup"><span data-stu-id="bf038-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="bf038-110">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bf038-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf038-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf038-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="bf038-112">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="bf038-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
