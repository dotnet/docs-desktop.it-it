---
title: 'Procedura: connettere più eventi a un singolo gestore eventi'
description: Informazioni su come connettere più eventi a un singolo gestore eventi in Windows Forms usando la visualizzazione eventi della Finestra Proprietà in C#.
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951363"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="814a2-103">Procedura: Connettere più eventi a un unico gestore eventi in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="814a2-103">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="814a2-104">Nella progettazione dell'applicazione, potrebbe essere necessario usare un singolo gestore eventi per più eventi o fare in modo che più eventi eseguano la stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="814a2-104">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="814a2-105">Ad esempio, si tratta spesso di un potente risparmio di tempo per fare in modo che un comando di menu generi lo stesso evento di un pulsante nel form, se espone la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="814a2-105">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="814a2-106">A tale scopo, è possibile usare la visualizzazione eventi del Finestra Proprietà in C# o la `Handles` parola chiave e le caselle a discesa **nome classe** e nome **Metodo** nell'editor del codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="814a2-106">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="814a2-107">Per connettere più eventi a un singolo gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="814a2-107">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="814a2-108">Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="814a2-108">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="814a2-109">Nella casella di riepilogo a discesa **nome classe** selezionare uno dei controlli per i quali si desidera disporre dell'handle del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="814a2-109">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="814a2-110">Nella casella di riepilogo a discesa **nome metodo** selezionare uno degli eventi che si desidera vengano gestiti dal gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="814a2-110">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="814a2-111">L'editor di codice inserisce il gestore eventi appropriato e posiziona il punto di inserimento all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="814a2-111">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="814a2-112">Nell'esempio seguente è l' <xref:System.Windows.Forms.Control.Click> evento per il <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="814a2-112">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="814a2-113">Aggiungere gli altri eventi che si desidera gestire alla `Handles` clausola.</span><span class="sxs-lookup"><span data-stu-id="814a2-113">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="814a2-114">Aggiungere il codice appropriato al gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="814a2-114">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="814a2-115">Per connettere più eventi a un singolo gestore eventi in C\#</span><span class="sxs-lookup"><span data-stu-id="814a2-115">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="814a2-116">Selezionare il controllo a cui si desidera connettere un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="814a2-116">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="814a2-117">Nella Finestra Proprietà fare clic sul pulsante **eventi** (![pulsante eventi](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="814a2-117">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="814a2-118">Fare clic sul nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="814a2-118">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="814a2-119">Nella sezione valore accanto al nome dell'evento, fare clic sul pulsante a discesa per visualizzare un elenco di gestori eventi esistenti che corrispondono alla firma del metodo dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="814a2-119">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="814a2-120">Selezionare il gestore eventi appropriato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="814a2-120">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="814a2-121">Il codice verrà aggiunto al form per associare l'evento al gestore eventi esistente.</span><span class="sxs-lookup"><span data-stu-id="814a2-121">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="814a2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="814a2-122">See also</span></span>

- [<span data-ttu-id="814a2-123">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="814a2-123">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="814a2-124">Panoramica sui gestori eventi</span><span class="sxs-lookup"><span data-stu-id="814a2-124">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
