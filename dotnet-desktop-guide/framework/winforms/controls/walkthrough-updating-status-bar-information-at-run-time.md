---
title: 'Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: a58f8698af95810e4f716aa2b105bb86be3f55e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964678"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="8969a-102">Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8969a-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8969a-103">I <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> controlli e sostituiscono e aggiungono funzionalità <xref:System.Windows.Forms.StatusBar> ai <xref:System.Windows.Forms.StatusBarPanel> controlli e; tuttavia, <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> controlli e vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="8969a-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="8969a-104">Spesso, in fase di esecuzione, un programma richiede di aggiornare in modo dinamico il contenuto dei pannelli della barra di stato in base alle modifiche dello stato dell'applicazione o all'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8969a-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="8969a-105">Si tratta di un metodo comune utilizzato per segnalare agli utenti che sono attivati tasti quali BLOC MAIUSC, BLOC NUM o BLOC SCORR oppure per fornire la data o un orologio come riferimento.</span><span class="sxs-lookup"><span data-stu-id="8969a-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="8969a-106">Nell'esempio seguente si userà un'istanza della <xref:System.Windows.Forms.StatusBarPanel> classe per ospitare un clock.</span><span class="sxs-lookup"><span data-stu-id="8969a-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="8969a-107">Per preparare la barra di stato per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="8969a-107">To get the status bar ready for updating</span></span>  
  
1. <span data-ttu-id="8969a-108">Creare un nuovo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8969a-108">Create a new Windows form.</span></span>  
  
2. <span data-ttu-id="8969a-109">Aggiungere un oggetto <xref:System.Windows.Forms.StatusBar> al form.</span><span class="sxs-lookup"><span data-stu-id="8969a-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="8969a-110">Per informazioni dettagliate, vedere [Procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8969a-110">For details, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
3. <span data-ttu-id="8969a-111">Aggiungere al controllo un pannello della barra di stato <xref:System.Windows.Forms.StatusBar> .</span><span class="sxs-lookup"><span data-stu-id="8969a-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="8969a-112">Per informazioni dettagliate, vedere [Procedura: aggiungere pannelli a un controllo StatusBar](how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="8969a-112">For details, see [How to: Add Panels to a StatusBar Control](how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4. <span data-ttu-id="8969a-113">Per il <xref:System.Windows.Forms.StatusBar> controllo aggiunto al form, impostare la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="8969a-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5. <span data-ttu-id="8969a-114">Aggiungere un <xref:System.Windows.Forms.Timer> componente Windows Forms al modulo.</span><span class="sxs-lookup"><span data-stu-id="8969a-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8969a-115">Il <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> componente Windows Forms è progettato per un ambiente Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8969a-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="8969a-116">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8969a-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
6. <span data-ttu-id="8969a-117">Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="8969a-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7. <span data-ttu-id="8969a-118">Impostare la <xref:System.Windows.Forms.Timer.Interval%2A> proprietà di <xref:System.Windows.Forms.Timer> su 30000.</span><span class="sxs-lookup"><span data-stu-id="8969a-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8969a-119">La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà del <xref:System.Windows.Forms.Timer> componente è impostata su 30 secondi (30.000 millisecondi) per garantire che venga riflessa un'ora esatta nel tempo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8969a-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="8969a-120">Per implementare il timer per l'aggiornamento della barra di stato</span><span class="sxs-lookup"><span data-stu-id="8969a-120">To implement the timer to update the status bar</span></span>  
  
1. <span data-ttu-id="8969a-121">Inserire il codice seguente nel gestore eventi del <xref:System.Windows.Forms.Timer> componente per aggiornare il pannello del <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="8969a-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="8969a-122">Ora è possibile eseguire l'applicazione per osservare l'orologio in funzione nel pannello della barra di stato.</span><span class="sxs-lookup"><span data-stu-id="8969a-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="8969a-123">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="8969a-123">To test the application</span></span>  
  
1. <span data-ttu-id="8969a-124">Effettuare il debug dell'applicazione, quindi premere F5 per eseguirla.</span><span class="sxs-lookup"><span data-stu-id="8969a-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="8969a-125">Per informazioni dettagliate sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span><span class="sxs-lookup"><span data-stu-id="8969a-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8969a-126">Sono richiesti circa 30 secondi per visualizzare l'orologio sulla barra di stato.</span><span class="sxs-lookup"><span data-stu-id="8969a-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="8969a-127">per ottenere l'ora più accurata possibile.</span><span class="sxs-lookup"><span data-stu-id="8969a-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="8969a-128">Viceversa, per far apparire il clock prima, è possibile ridurre il valore della <xref:System.Windows.Forms.Timer.Interval%2A> proprietà impostata nel passaggio 7 della procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="8969a-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8969a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8969a-129">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="8969a-130">Procedura: Aggiungere pannelli a un controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="8969a-130">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)
- [<span data-ttu-id="8969a-131">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8969a-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="8969a-132">Panoramica del controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="8969a-132">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
