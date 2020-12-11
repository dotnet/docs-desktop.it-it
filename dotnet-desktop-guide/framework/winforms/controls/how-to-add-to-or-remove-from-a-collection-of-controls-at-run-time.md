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
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="a0be7-103">Procedura: Aggiungere o rimuovere controlli da una raccolta in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a0be7-103">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>

<span data-ttu-id="a0be7-104">Le attività comuni nello sviluppo di applicazioni sono l'aggiunta e la rimozione di controlli da qualsiasi controllo contenitore nei form, ad esempio il <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> controllo o o anche il form stesso.</span><span class="sxs-lookup"><span data-stu-id="a0be7-104">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="a0be7-105">In fase di progettazione è possibile trascinare i controlli direttamente in un pannello o una casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a0be7-105">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="a0be7-106">In fase di esecuzione questi controlli mantengono una raccolta `Controls`, che tiene traccia di quali controlli vengono posizionati su essi.</span><span class="sxs-lookup"><span data-stu-id="a0be7-106">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0be7-107">L'esempio di codice seguente si applica a qualsiasi controllo che mantiene una raccolta di controlli al suo interno.</span><span class="sxs-lookup"><span data-stu-id="a0be7-107">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="a0be7-108">Per aggiungere un controllo a una raccolta a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a0be7-108">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="a0be7-109">Creare un'istanza del controllo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a0be7-109">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="a0be7-110">Impostare le proprietà del nuovo controllo.</span><span class="sxs-lookup"><span data-stu-id="a0be7-110">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="a0be7-111">Aggiungere il controllo alla raccolta `Controls` del controllo padre.</span><span class="sxs-lookup"><span data-stu-id="a0be7-111">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="a0be7-112">Nell'esempio di codice seguente viene illustrato come creare un'istanza del <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="a0be7-112">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="a0be7-113">Richiede un modulo con un <xref:System.Windows.Forms.Panel> controllo e che il metodo di gestione degli eventi per il pulsante creato, `NewPanelButton_Click` , esista già.</span><span class="sxs-lookup"><span data-stu-id="a0be7-113">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="a0be7-114">Per rimuovere controlli da una raccolta a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a0be7-114">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="a0be7-115">Rimuovere il gestore eventi dall'evento.</span><span class="sxs-lookup"><span data-stu-id="a0be7-115">Remove the event handler from the event.</span></span> <span data-ttu-id="a0be7-116">In Visual Basic usare la parola chiave dell' [istruzione RemoveHandler](/dotnet/visual-basic/language-reference/statements/removehandler-statement) . in C# usare l' [operatore-=](/dotnet/csharp/language-reference/operators/subtraction-operator).</span><span class="sxs-lookup"><span data-stu-id="a0be7-116">In Visual Basic, use the [RemoveHandler Statement](/dotnet/visual-basic/language-reference/statements/removehandler-statement) keyword; in C#, use the [-= operator](/dotnet/csharp/language-reference/operators/subtraction-operator).</span></span>  
  
2. <span data-ttu-id="a0be7-117">Usare il metodo `Remove` per eliminare il controllo desiderato dalla raccolta del pannello `Controls`.</span><span class="sxs-lookup"><span data-stu-id="a0be7-117">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="a0be7-118">Chiamare il <xref:System.Windows.Forms.Control.Dispose%2A> metodo per rilasciare tutte le risorse usate dal controllo.</span><span class="sxs-lookup"><span data-stu-id="a0be7-118">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0be7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0be7-119">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="a0be7-120">Controllo del pannello</span><span class="sxs-lookup"><span data-stu-id="a0be7-120">Panel Control</span></span>](panel-control-windows-forms.md)
