---
title: Modificare l'aspetto del controllo LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961987"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Forms
È possibile modificare il testo visualizzato dal <xref:System.Windows.Forms.LinkLabel> controllo per adattarlo a diversi scopi. Ad esempio, è pratica comune indicare all'utente che è possibile fare clic su testo impostando il testo in modo che venga visualizzato in un colore specifico con una sottolineatura. Dopo che l'utente fa clic sul testo, il colore diventa un colore diverso. Per controllare questo comportamento, è possibile impostare cinque proprietà diverse: le <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà,, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> , <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> e <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> .  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Per modificare l'aspetto di un controllo LinkLabel  
  
1. Impostare le <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> proprietà e sui <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> colori desiderati.  
  
     Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. Impostare la <xref:System.Windows.Forms.LinkLabel.Text%2A> proprietà su una didascalia appropriata.  
  
     Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Impostare la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà per determinare la parte della didascalia che verrà indicata come collegamento.  
  
     Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valore è rappresentato da un oggetto <xref:System.Windows.Forms.LinkArea> contenente due numeri, la posizione iniziale del carattere e il numero di caratteri. Questa operazione può essere eseguita a livello di programmazione o in fase di progettazione nella finestra **Proprietà** .  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Impostare la <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> proprietà su <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> , <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline> .  
  
     Se è impostato su <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> , la parte della didascalia determinata da <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> sarà sottolineata solo quando il puntatore viene posizionato su di esso.  
  
5. Nel <xref:System.Windows.Forms.LinkLabel.LinkClicked> gestore eventi impostare la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> proprietà su `true` .  
  
     Quando è stato visitato un collegamento, è pratica comune modificarne l'aspetto in qualche modo, in genere in base al colore. Il testo cambierà in base al colore specificato dalla <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Proprietà.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Panoramica del controllo LinkLabel](linklabel-control-overview-windows-forms.md)
- [Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Controllo LinkLabel](linklabel-control-windows-forms.md)
