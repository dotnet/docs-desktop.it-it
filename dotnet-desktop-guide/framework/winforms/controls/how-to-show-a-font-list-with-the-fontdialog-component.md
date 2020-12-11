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
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="3bc43-102">Procedura: Visualizzare un elenco di tipi di carattere con il componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="3bc43-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="3bc43-103">Il componente [FontDialog](fontdialog-component-windows-forms.md) consente agli utenti di selezionare un tipo di carattere, nonché di modificarne gli aspetti di visualizzazione, ad esempio il peso e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3bc43-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="3bc43-104">Il tipo di carattere selezionato nella finestra di dialogo viene restituito nella <xref:System.Windows.Forms.FontDialog.Font%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3bc43-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="3bc43-105">Pertanto, l'utilizzo del tipo di carattere selezionato dall'utente è semplice quanto la lettura di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3bc43-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="3bc43-106">Per selezionare le proprietà del tipo di carattere utilizzando il componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="3bc43-106">To select font properties using the FontDialog Component</span></span>  
  
1. <span data-ttu-id="3bc43-107">Consente di visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3bc43-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="3bc43-108">Utilizzare la <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità di chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3bc43-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="3bc43-109">Utilizzare la <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà per impostare il tipo di carattere desiderato.</span><span class="sxs-lookup"><span data-stu-id="3bc43-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="3bc43-110">Nell'esempio seguente il <xref:System.Windows.Forms.Button> gestore eventi del controllo <xref:System.Windows.Forms.Control.Click> apre un <xref:System.Windows.Forms.FontDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="3bc43-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="3bc43-111">Quando si sceglie un tipo di carattere e l'utente fa clic su **OK**, la <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà di un <xref:System.Windows.Forms.TextBox> controllo che si trova nel form viene impostata sul tipo di carattere scelto.</span><span class="sxs-lookup"><span data-stu-id="3bc43-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="3bc43-112">Nell'esempio si presuppone che il form disponga di un <xref:System.Windows.Forms.Button> controllo, di un  <xref:System.Windows.Forms.TextBox> controllo e di un <xref:System.Windows.Forms.FontDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="3bc43-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="3bc43-113">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="3bc43-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3bc43-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bc43-114">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="3bc43-115">Componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="3bc43-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
