---
title: 'Procedura: Aggiungere o rimuovere controlli da una raccolta in fase di esecuzione'
description: Informazioni su come aggiungere e rimuovere controlli da qualsiasi controllo contenitore nei form, ad esempio il pannello o il controllo GroupBox, o anche il form stesso.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 2d6d99cdeca6274d86148113cf1b902f8f70804a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963604"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Procedura: Aggiungere o rimuovere controlli da una raccolta in fase di esecuzione

Le attività comuni nello sviluppo di applicazioni sono l'aggiunta e la rimozione di controlli da qualsiasi controllo contenitore nei form, ad esempio il <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> controllo o o anche il form stesso. In fase di progettazione è possibile trascinare i controlli direttamente in un pannello o una casella di gruppo. In fase di esecuzione questi controlli mantengono una raccolta `Controls`, che tiene traccia di quali controlli vengono posizionati su essi.  
  
> [!NOTE]
> L'esempio di codice seguente si applica a qualsiasi controllo che mantiene una raccolta di controlli al suo interno.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Per aggiungere un controllo a una raccolta a livello di codice  
  
1. Creare un'istanza del controllo da aggiungere.  
  
2. Impostare le proprietà del nuovo controllo.  
  
3. Aggiungere il controllo alla raccolta `Controls` del controllo padre.  
  
     Nell'esempio di codice seguente viene illustrato come creare un'istanza del <xref:System.Windows.Forms.Button> controllo. Richiede un modulo con un <xref:System.Windows.Forms.Panel> controllo e che il metodo di gestione degli eventi per il pulsante creato, `NewPanelButton_Click` , esista già.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>Per rimuovere controlli da una raccolta a livello di codice  
  
1. Rimuovere il gestore eventi dall'evento. In Visual Basic usare la parola chiave dell' [istruzione RemoveHandler](/dotnet/visual-basic/language-reference/statements/removehandler-statement) . in C# usare l' [operatore-=](/dotnet/csharp/language-reference/operators/subtraction-operator).  
  
2. Usare il metodo `Remove` per eliminare il controllo desiderato dalla raccolta del pannello `Controls`.  
  
3. Chiamare il <xref:System.Windows.Forms.Control.Dispose%2A> metodo per rilasciare tutte le risorse usate dal controllo.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Panel>
- [Controllo del pannello](panel-control-windows-forms.md)
