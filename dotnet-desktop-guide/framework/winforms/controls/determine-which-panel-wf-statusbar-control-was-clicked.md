---
title: Determinare il pannello in cui è stato fatto clic sul controllo StatusBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950994"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="97b3f-102">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97b3f-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="97b3f-103">I <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> controlli e sostituiscono e aggiungono funzionalità <xref:System.Windows.Forms.StatusBar> ai <xref:System.Windows.Forms.StatusBarPanel> controlli e; tuttavia, <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> controlli e vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="97b3f-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="97b3f-104">Per programmare il controllo di [controllo StatusBar](statusbar-control-windows-forms.md) per rispondere ai clic dell'utente, usare un'istruzione case all'interno dell' <xref:System.Windows.Forms.StatusBar.PanelClick> evento.</span><span class="sxs-lookup"><span data-stu-id="97b3f-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="97b3f-105">L'evento contiene un argomento (argomento Panel), che contiene un riferimento all'oggetto selezionato <xref:System.Windows.Forms.StatusBarPanel> .</span><span class="sxs-lookup"><span data-stu-id="97b3f-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="97b3f-106">Utilizzando questo riferimento, è possibile determinare l'indice del pannello selezionato e programmare di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="97b3f-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97b3f-107">Verificare che la <xref:System.Windows.Forms.StatusBar> proprietà del controllo <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> sia impostata su `true` .</span><span class="sxs-lookup"><span data-stu-id="97b3f-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="97b3f-108">Per determinare il pannello selezionato</span><span class="sxs-lookup"><span data-stu-id="97b3f-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="97b3f-109">Nel <xref:System.Windows.Forms.StatusBar.PanelClick> gestore dell'evento usare un' `Select Case` istruzione (in Visual Basic) o `switch case` (Visual C# o Visual C++) per determinare il pannello su cui è stato fatto clic esaminando l'indice del pannello selezionato negli argomenti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="97b3f-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="97b3f-110">Nell'esempio di codice seguente è richiesta la presenza, nel form, di un <xref:System.Windows.Forms.StatusBar> controllo, `StatusBar1` , e di due <xref:System.Windows.Forms.StatusBarPanel> oggetti, `StatusBarPanel1` e `StatusBarPanel2` .</span><span class="sxs-lookup"><span data-stu-id="97b3f-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="97b3f-111">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="97b3f-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97b3f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97b3f-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="97b3f-113">Procedura: Impostare la dimensione dei pannelli della barra di stato</span><span class="sxs-lookup"><span data-stu-id="97b3f-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="97b3f-114">Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="97b3f-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="97b3f-115">Panoramica del controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="97b3f-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
