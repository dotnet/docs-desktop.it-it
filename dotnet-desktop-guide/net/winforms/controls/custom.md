---
title: Tipi di controlli personalizzati
description: Informazioni sui diversi tipi di controlli personalizzati che è possibile creare in Windows Forms per .NET.
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- UserControl
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 25430adf6efbb4c1f323496ce46cdea5aa0bb95c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967315"
---
# <a name="types-of-custom-controls-windows-forms-net"></a><span data-ttu-id="ff727-103">Tipi di controlli personalizzati (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="ff727-103">Types of custom controls (Windows Forms .NET)</span></span>

<span data-ttu-id="ff727-104">Con Windows Forms è possibile sviluppare e implementare nuovi controlli.</span><span class="sxs-lookup"><span data-stu-id="ff727-104">With Windows Forms, you can develop and implement new controls.</span></span> <span data-ttu-id="ff727-105">È possibile creare un nuovo controllo utente, modificare i controlli esistenti tramite ereditarietà e scrivere un controllo personalizzato che esegue il proprio disegno.</span><span class="sxs-lookup"><span data-stu-id="ff727-105">You can create a new user control, modify existing controls through inheritance, and write a custom control that does its own painting.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="ff727-106">Decidere quale tipo di controllo creare può generare confusione.</span><span class="sxs-lookup"><span data-stu-id="ff727-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="ff727-107">In questo articolo vengono evidenziate le differenze tra i vari tipi di controlli da cui è possibile ereditare e vengono fornite informazioni su come scegliere un particolare tipo di controllo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ff727-107">This article highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular type of control for your project.</span></span>

<table>
<thead>
  <tr>
    <th><span data-ttu-id="ff727-108">Se...</span><span class="sxs-lookup"><span data-stu-id="ff727-108">If ...</span></span></th>
    <th><span data-ttu-id="ff727-109">Crea...</span><span class="sxs-lookup"><span data-stu-id="ff727-109">Create a ...</span></span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="ff727-110">Combinare le funzionalità di vari controlli di Windows Form in una singola unità riusabile.</span><span class="sxs-lookup"><span data-stu-id="ff727-110">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="ff727-111"><a href="#composite-controls">Controllo composito</a> ereditando da <a href="/dotnet/api/system.windows.forms.usercontrol">System. Windows. Forms. UserControl</a>.</span><span class="sxs-lookup"><span data-stu-id="ff727-111"><a href="#composite-controls">Composite control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a>.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="ff727-112">Molte delle funzionalità necessarie sono identiche a quelle incluse in un controllo di Windows Form esistente.</span><span class="sxs-lookup"><span data-stu-id="ff727-112">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span></li>
            <li><span data-ttu-id="ff727-113">Non è necessaria un'interfaccia utente grafica personalizzata oppure si vuole progettare una nuova interfaccia utente grafica per un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="ff727-113">You don't need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="ff727-114"><a href="#extended-controls">Controllo esteso</a> ereditando da un controllo Windows Forms specifico.</span><span class="sxs-lookup"><span data-stu-id="ff727-114"><a href="#extended-controls">Extended control</a> by inheriting from a specific Windows Forms control.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="ff727-115">Fornire una rappresentazione grafica personalizzata del controllo.</span><span class="sxs-lookup"><span data-stu-id="ff727-115">You want to provide a custom graphical representation of your control.</span></span></li>
            <li><span data-ttu-id="ff727-116">È necessario implementare una funzionalità personalizzata non disponibile tramite i controlli standard.</span><span class="sxs-lookup"><span data-stu-id="ff727-116">You need to implement custom functionality that isn't available through standard controls.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="ff727-117"><a href="#custom-controls">Controllo personalizzato</a> mediante l'ereditarietà da <a href="/dotnet/api/system.windows.forms.control">System. Windows. Forms. Control</a>.</span><span class="sxs-lookup"><span data-stu-id="ff727-117"><a href="#custom-controls">Custom control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a>.</span></span></td>
  </tr>
</tbody>
</table>

## <a name="base-control-class"></a><span data-ttu-id="ff727-118">Classe di base del controllo</span><span class="sxs-lookup"><span data-stu-id="ff727-118">Base Control Class</span></span>

<span data-ttu-id="ff727-119">La <xref:System.Windows.Forms.Control> classe è la classe base per i controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff727-119">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="ff727-120">Fornisce l'infrastruttura necessaria per la visualizzazione visiva nelle applicazioni Windows Forms e offre le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff727-120">It provides the infrastructure required for visual display in Windows Forms applications and provides the following capabilities:</span></span>

- <span data-ttu-id="ff727-121">Espone un handle di finestra.</span><span class="sxs-lookup"><span data-stu-id="ff727-121">Exposes a window handle.</span></span>
- <span data-ttu-id="ff727-122">Gestisce il routing dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ff727-122">Manages message routing.</span></span>
- <span data-ttu-id="ff727-123">Genera gli eventi di mouse e tastiera e molti altri eventi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ff727-123">Provides mouse and keyboard events, and many other user interface events.</span></span>
- <span data-ttu-id="ff727-124">Genera le funzionalità di layout avanzate.</span><span class="sxs-lookup"><span data-stu-id="ff727-124">Provides advanced layout features.</span></span>
- <span data-ttu-id="ff727-125">Contiene molte proprietà specifiche per la visualizzazione visiva, ad esempio <xref:System.Windows.Forms.Control.ForeColor%2A> ,, <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A> e <xref:System.Windows.Forms.Control.Width%2A> .</span><span class="sxs-lookup"><span data-stu-id="ff727-125">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>
- <span data-ttu-id="ff727-126">Offre la protezione e il supporto del threading necessari affinché un controllo Windows Form funzioni come un controllo Microsoft® ActiveX®.</span><span class="sxs-lookup"><span data-stu-id="ff727-126">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>

<span data-ttu-id="ff727-127">Poiché la maggior parte dell'infrastruttura viene fornita dalla classe base, è relativamente facile sviluppare controlli Windows Forms personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ff727-127">Because so much of the infrastructure is provided by the base class, it's relatively easy to develop your own Windows Forms controls.</span></span>

## <a name="composite-controls"></a><span data-ttu-id="ff727-128">Controlli compositi</span><span class="sxs-lookup"><span data-stu-id="ff727-128">Composite Controls</span></span>

<span data-ttu-id="ff727-129">Un controllo composito è una raccolta di controlli Windows Form incapsulata in un contenitore comune.</span><span class="sxs-lookup"><span data-stu-id="ff727-129">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="ff727-130">Questo tipo di controllo viene talvolta definito *controllo utente*.</span><span class="sxs-lookup"><span data-stu-id="ff727-130">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="ff727-131">I controlli contenuti vengono chiamati *controlli costitutivi*.</span><span class="sxs-lookup"><span data-stu-id="ff727-131">The contained controls are called *constituent controls*.</span></span>

<span data-ttu-id="ff727-132">Un controllo composito include tutte le funzionalità intrinseche associate a ogni controllo Windows Form contenuto e consente di esporre e associare in modo selettivo le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="ff727-132">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="ff727-133">Un controllo composito mette inoltre a disposizione numerose funzionalità predefinite di gestione della tastiera senza richiedere ulteriori operazioni di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ff727-133">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>

<span data-ttu-id="ff727-134">Ad esempio, un controllo composito potrebbe essere compilato per visualizzare i dati dell'indirizzo del cliente da un database.</span><span class="sxs-lookup"><span data-stu-id="ff727-134">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="ff727-135">Questo controllo include un <xref:System.Windows.Forms.DataGridView> controllo per visualizzare i campi del database, un oggetto <xref:System.Windows.Forms.BindingSource> per gestire l'associazione a un'origine dati e un <xref:System.Windows.Forms.BindingNavigator> controllo per spostarsi tra i record.</span><span class="sxs-lookup"><span data-stu-id="ff727-135">This control would include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="ff727-136">È possibile esporre le proprietà di data binding in modo selettivo, nonché includere l'intero controllo in un pacchetto e riusarlo nelle diverse applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ff727-136">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span><!-- TODO For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).-->

<span data-ttu-id="ff727-137">Per creare un controllo composito, derivare dalla <xref:System.Windows.Forms.UserControl> classe.</span><span class="sxs-lookup"><span data-stu-id="ff727-137">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="ff727-138">La <xref:System.Windows.Forms.UserControl> classe base fornisce il routing della tastiera per i controlli figlio e consente ai controlli figlio di funzionare come un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ff727-138">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span><!-- TODO For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).-->

## <a name="extended-controls"></a><span data-ttu-id="ff727-139">Controlli estesi</span><span class="sxs-lookup"><span data-stu-id="ff727-139">Extended Controls</span></span>

<span data-ttu-id="ff727-140">È possibile derivare un controllo ereditato da un controllo di Windows Form esistente.</span><span class="sxs-lookup"><span data-stu-id="ff727-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="ff727-141">Con questo approccio è possibile mantenere tutte le funzionalità intrinseche di un controllo Windows Forms e quindi estendere tale funzionalità aggiungendo proprietà, metodi o altre funzionalità personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ff727-141">With this approach, you can keep all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="ff727-142">Con questa opzione è possibile eseguire l'override della logica di disegno del controllo di base e quindi estendere la relativa interfaccia utente modificandone l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="ff727-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>

<span data-ttu-id="ff727-143">Ad esempio, è possibile creare un controllo derivato dal <xref:System.Windows.Forms.Button> controllo che tiene traccia del numero di volte in cui un utente ha fatto clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="ff727-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>

<span data-ttu-id="ff727-144">In alcuni controlli è inoltre possibile aggiungere un aspetto personalizzato all'interfaccia utente grafica del controllo eseguendo l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base.</span><span class="sxs-lookup"><span data-stu-id="ff727-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="ff727-145">Per un pulsante esteso che tiene traccia dei clic, è possibile eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per chiamare l'implementazione di base di <xref:System.Windows.Forms.Control.OnPaint%2A> , quindi tracciare il conteggio dei clic in un angolo dell' <xref:System.Windows.Forms.Button> area client del controllo.</span><span class="sxs-lookup"><span data-stu-id="ff727-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>

## <a name="custom-controls"></a><span data-ttu-id="ff727-146">Controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="ff727-146">Custom Controls</span></span>

<span data-ttu-id="ff727-147">Un altro modo per creare un controllo consiste nel crearne uno sostanzialmente dall'inizio ereditando da <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="ff727-147">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ff727-148">La <xref:System.Windows.Forms.Control> classe fornisce tutte le funzionalità di base richieste dai controlli, inclusi gli eventi di gestione del mouse e della tastiera, ma nessuna funzionalità specifica del controllo o un'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="ff727-148">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>

<span data-ttu-id="ff727-149">La creazione di un controllo mediante l'ereditarietà dalla <xref:System.Windows.Forms.Control> classe richiede un maggior numero di pensieri e sforzi rispetto a ereditare da <xref:System.Windows.Forms.UserControl> o da un controllo Windows Forms esistente.</span><span class="sxs-lookup"><span data-stu-id="ff727-149">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="ff727-150">Poiché gran parte dell'implementazione spetta all'utente, il controllo può avere maggiore flessibilità rispetto a un controllo composito o esteso ed è possibile personalizzarlo in modo da soddisfare le esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="ff727-150">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>

<span data-ttu-id="ff727-151">Per implementare un controllo personalizzato, è necessario scrivere il codice per l' <xref:System.Windows.Forms.Control.OnPaint%2A> evento del controllo, nonché qualsiasi codice specifico della funzionalità necessario.</span><span class="sxs-lookup"><span data-stu-id="ff727-151">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="ff727-152">È anche possibile eseguire l'override del <xref:System.Windows.Forms.Control.WndProc%2A> metodo e gestire direttamente i messaggi di Windows.</span><span class="sxs-lookup"><span data-stu-id="ff727-152">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="ff727-153">Questo è il modo più potente di creare un controllo, ma per usare questa tecnica in modo efficace, è necessario avere familiarità con l'API Microsoft Win32®.</span><span class="sxs-lookup"><span data-stu-id="ff727-153">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>

<span data-ttu-id="ff727-154">Un esempio di controllo personalizzato è un controllo clock che duplica l'aspetto e il funzionamento di un orologio analogico.</span><span class="sxs-lookup"><span data-stu-id="ff727-154">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="ff727-155">Il disegno personalizzato viene richiamato per fare in modo che le lancette dell'orologio si sposti in risposta a <xref:System.Windows.Forms.Timer.Tick> eventi di un <xref:System.Windows.Forms.Timer> componente interno.</span><span class="sxs-lookup"><span data-stu-id="ff727-155">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span><!-- TODO For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).-->

## <a name="activex-controls"></a><span data-ttu-id="ff727-156">Controlli ActiveX</span><span class="sxs-lookup"><span data-stu-id="ff727-156">ActiveX Controls</span></span>

<span data-ttu-id="ff727-157">Anche se l'infrastruttura di Windows Form è stata ottimizzata per ospitare i controlli Windows Form, è comunque possibile usare i controlli ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ff727-157">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="ff727-158">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff727-158">There's support for this task in Visual Studio.</span></span><!-- TODO For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).-->

## <a name="windowless-controls"></a><span data-ttu-id="ff727-159">Controlli senza finestra</span><span class="sxs-lookup"><span data-stu-id="ff727-159">Windowless Controls</span></span>

<span data-ttu-id="ff727-160">Le tecnologie Microsoft Visual Basic® 6,0 e ActiveX supportano i controlli *privi di finestra* .</span><span class="sxs-lookup"><span data-stu-id="ff727-160">The Microsoft Visual Basic® 6.0 and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="ff727-161">I controlli senza finestra non sono supportati in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff727-161">Windowless controls aren't supported in Windows Forms.</span></span>

## <a name="custom-design-experience"></a><span data-ttu-id="ff727-162">Esperienza di progettazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="ff727-162">Custom Design Experience</span></span>

<span data-ttu-id="ff727-163">Se è necessario implementare una soluzione personalizzata in fase di progettazione, è possibile creare una propria finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ff727-163">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="ff727-164">Per i controlli compositi, derivare la classe della finestra di progettazione personalizzata dalle <xref:System.Windows.Forms.Design.ParentControlDesigner> <xref:System.Windows.Forms.Design.DocumentDesigner> classi o.</span><span class="sxs-lookup"><span data-stu-id="ff727-164">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="ff727-165">Per i controlli estesi e personalizzati, derivare la classe della finestra di progettazione personalizzata dalla <xref:System.Windows.Forms.Design.ControlDesigner> classe.</span><span class="sxs-lookup"><span data-stu-id="ff727-165">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>

<span data-ttu-id="ff727-166">Usare <xref:System.ComponentModel.DesignerAttribute> per associare il controllo alla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ff727-166">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span>

<span data-ttu-id="ff727-167">Le informazioni seguenti non sono aggiornate, ma possono essere utili.</span><span class="sxs-lookup"><span data-stu-id="ff727-167">The following information is out of date but may help you.</span></span>

- <span data-ttu-id="ff727-168">[(Visual Studio 2013) estensione del supporto di Design-Time](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="ff727-168">[(Visual Studio 2013) Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>
- <span data-ttu-id="ff727-169">[(Visual Studio 2013) procedura: creare un controllo Windows Forms che sfrutta i vantaggi delle funzionalità di Design-Time](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="ff727-169">[(Visual Studio 2013) How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff727-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff727-170">See also</span></span>

- [<span data-ttu-id="ff727-171">Cenni preliminari sull'utilizzo di controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="ff727-171">Overview of Using Controls (Windows Forms .NET)</span></span>](overview.md)

<!-- TODO: link to the ..\custom-controls\ content 

- [Developing Custom Windows Forms Controls](developing-custom-windows-forms-controls.md)
- [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md)
- [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md)
-->
