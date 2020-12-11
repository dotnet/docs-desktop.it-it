---
title: Simulare eventi di tastiera
description: Informazioni su come simulare gli eventi di tastiera in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 5ac62ca4311461ba95a2c31876d038baffe678a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969259"
---
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a><span data-ttu-id="6517a-103">Come simulare gli eventi di tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="6517a-103">How to simulate keyboard events (Windows Forms .NET)</span></span>

<span data-ttu-id="6517a-104">Windows Forms fornisce alcune opzioni per simulare a livello di codice l'input da tastiera.</span><span class="sxs-lookup"><span data-stu-id="6517a-104">Windows Forms provides a few options for programmatically simulating keyboard input.</span></span> <span data-ttu-id="6517a-105">Questo articolo fornisce una panoramica di queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="6517a-105">This article provides an overview of these options.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a><span data-ttu-id="6517a-106">USA SendKeys</span><span class="sxs-lookup"><span data-stu-id="6517a-106">Use SendKeys</span></span>

<span data-ttu-id="6517a-107">Windows Forms fornisce la <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> classe per l'invio di sequenze di tasti all'applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="6517a-107">Windows Forms provides the <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> class for sending keystrokes to the active application.</span></span> <span data-ttu-id="6517a-108">Esistono due metodi per inviare le sequenze di tasti a un'applicazione: <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6517a-108">There are two methods to send keystrokes to an application: <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6517a-109">La differenza tra i due metodi è che `SendWait` blocca il thread corrente quando viene inviata la sequenza di tasti, in attesa di una risposta, mentre non lo è `Send` .</span><span class="sxs-lookup"><span data-stu-id="6517a-109">The difference between the two methods is that `SendWait` blocks the current thread when the keystroke is sent, waiting for a response, while `Send` doesn't.</span></span> <span data-ttu-id="6517a-110">Per ulteriori informazioni su `SendWait` , vedere [per inviare una sequenza di tasti a un'altra applicazione](#to-send-a-keystroke-to-a-different-application).</span><span class="sxs-lookup"><span data-stu-id="6517a-110">For more information about `SendWait`, see [To send a keystroke to a different application](#to-send-a-keystroke-to-a-different-application).</span></span>

> [!CAUTION]
> <span data-ttu-id="6517a-111">Se l'applicazione verrà usata a livello internazionale con un'ampia gamma di tastiere, è opportuno evitare l'uso di <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> perché potrebbe generare risultati imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="6517a-111">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

<span data-ttu-id="6517a-112">Dietro le quinte, `SendKeys` Usa un'implementazione di Windows precedente per l'invio dell'input, che può avere esito negativo nelle finestre moderne in cui si prevede che l'applicazione non sia in esecuzione con diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="6517a-112">Behind the scenes, `SendKeys` uses an older Windows implementation for sending input, which may fail on modern Windows where it's expected that the application isn't running with administrative rights.</span></span> <span data-ttu-id="6517a-113">Se l'implementazione precedente ha esito negativo, il codice tenta automaticamente l'implementazione di Windows più recente per l'invio dell'input.</span><span class="sxs-lookup"><span data-stu-id="6517a-113">If the older implementation fails, the code automatically tries the newer Windows implementation for sending input.</span></span> <span data-ttu-id="6517a-114">Inoltre, quando la <xref:System.Windows.Forms.SendKeys> classe usa la nuova implementazione, il <xref:System.Windows.Forms.SendKeys.SendWait%2A> metodo non blocca più il thread corrente durante l'invio di sequenze di tasti a un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="6517a-114">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method no longer blocks the current thread when sending keystrokes to another application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6517a-115">Se l'applicazione si basa su un comportamento coerente indipendentemente dal sistema operativo, è possibile forzare la classe <xref:System.Windows.Forms.SendKeys> a usare la nuova implementazione aggiungendo la seguente impostazione applicazione al file app.config.</span><span class="sxs-lookup"><span data-stu-id="6517a-115">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="6517a-116">Per forzare la <xref:System.Windows.Forms.SendKeys> classe a usare _solo_ l'implementazione precedente, usare invece il valore `"JournalHook"` .</span><span class="sxs-lookup"><span data-stu-id="6517a-116">To force the <xref:System.Windows.Forms.SendKeys> class to _only_ use the previous implementation, use the value `"JournalHook"` instead.</span></span>

### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="6517a-117">Per inviare una pressione di tasto alla stessa applicazione</span><span class="sxs-lookup"><span data-stu-id="6517a-117">To send a keystroke to the same application</span></span>

<span data-ttu-id="6517a-118">Chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> della classe <xref:System.Windows.Forms.SendKeys> .</span><span class="sxs-lookup"><span data-stu-id="6517a-118">Call the <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="6517a-119">Le pressioni di tasti specificate verranno ricevute dal controllo attivo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6517a-119">The specified keystrokes will be received by the active control of the application.</span></span>

<span data-ttu-id="6517a-120">Nell'esempio di codice seguente viene usato `Send` per simulare la pressione dei tasti <kbd>ALT</kbd> e <kbd>giù</kbd> insieme.</span><span class="sxs-lookup"><span data-stu-id="6517a-120">The following code example uses `Send` to simulate pressing the <kbd>ALT</kbd> and <kbd>DOWN</kbd> keys together.</span></span> <span data-ttu-id="6517a-121">Queste sequenze di tasti fanno sì <xref:System.Windows.Forms.ComboBox> che il controllo visualizzi l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6517a-121">These keystrokes cause the <xref:System.Windows.Forms.ComboBox> control to display its dropdown.</span></span> <span data-ttu-id="6517a-122">In questo esempio si presuppone una <xref:System.Windows.Forms.Form> con <xref:System.Windows.Forms.Button> e <xref:System.Windows.Forms.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="6517a-122">This example assumes a <xref:System.Windows.Forms.Form> with a <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.ComboBox>.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="6517a-123">Per inviare una pressione di tasto a un'applicazione diversa</span><span class="sxs-lookup"><span data-stu-id="6517a-123">To send a keystroke to a different application</span></span>

<span data-ttu-id="6517a-124">I <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> metodi e inviano sequenze di tasti all'applicazione attiva, che in genere è l'applicazione da cui si stanno inviando le sequenze di tasti.</span><span class="sxs-lookup"><span data-stu-id="6517a-124">The <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> methods send keystrokes to the active application, which is usually the application you're sending keystrokes from.</span></span> <span data-ttu-id="6517a-125">Per inviare sequenze di tasti a un'altra applicazione, è prima necessario attivarla.</span><span class="sxs-lookup"><span data-stu-id="6517a-125">To send keystrokes to another application, you first need to activate it.</span></span> <span data-ttu-id="6517a-126">Poiché non esiste alcun metodo gestito per attivare un'altra applicazione, è necessario usare i metodi Windows nativi per concentrare l'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="6517a-126">Because there's no managed method to activate another application, you must use native Windows methods to focus the other application.</span></span> <span data-ttu-id="6517a-127">Il seguente esempio di codice usa platform invoke per chiamare i metodi `FindWindow` e `SetForegroundWindow` per attivare la finestra dell'applicazione Calculator e quindi chiama `Send` per inviare una serie di calcoli all'applicazione Calculator.</span><span class="sxs-lookup"><span data-stu-id="6517a-127">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls `Send` to issue a series of calculations to the Calculator application.</span></span>

<span data-ttu-id="6517a-128">L'esempio di codice seguente usa `Send` per simulare la pressione dei tasti nell'applicazione Windows 10 Calculator.</span><span class="sxs-lookup"><span data-stu-id="6517a-128">The following code example uses `Send` to simulate pressing keys into the Windows 10 Calculator application.</span></span> <span data-ttu-id="6517a-129">Cerca innanzitutto una finestra dell'applicazione con titolo `Calculator` e quindi la attiva.</span><span class="sxs-lookup"><span data-stu-id="6517a-129">It first searches for an application window with title of `Calculator` and then activates it.</span></span> <span data-ttu-id="6517a-130">Una volta attivato, le sequenze di tasti vengono inviate per calcolare 10 più 10.</span><span class="sxs-lookup"><span data-stu-id="6517a-130">Once activated, the keystrokes are sent to calculate 10 plus 10.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a><span data-ttu-id="6517a-131">Usare i metodi OnEventName</span><span class="sxs-lookup"><span data-stu-id="6517a-131">Use OnEventName methods</span></span>

<span data-ttu-id="6517a-132">Il modo più semplice per simulare gli eventi della tastiera consiste nel chiamare un metodo sull'oggetto che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="6517a-132">The easiest way to simulate keyboard events is to call a method on the object that raises the event.</span></span> <span data-ttu-id="6517a-133">La maggior parte degli eventi dispone di un metodo corrispondente che li richiama, denominato nel modello di `On` seguito da `EventName` , ad esempio `OnKeyPress` .</span><span class="sxs-lookup"><span data-stu-id="6517a-133">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnKeyPress`.</span></span> <span data-ttu-id="6517a-134">Questa opzione è possibile solo all'interno di controlli o moduli personalizzati, perché questi metodi sono protetti e non è possibile accedervi dall'esterno del contesto del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="6517a-134">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span>

<span data-ttu-id="6517a-135">Questi metodi protetti sono disponibili per simulare gli eventi della tastiera.</span><span class="sxs-lookup"><span data-stu-id="6517a-135">These protected methods are available to simulate keyboard events.</span></span>

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

<span data-ttu-id="6517a-136">Per ulteriori informazioni su questi eventi, vedere [utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md).</span><span class="sxs-lookup"><span data-stu-id="6517a-136">For more information about these events, see [Using keyboard events (Windows Forms .NET)](events.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6517a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6517a-137">See also</span></span>

- [<span data-ttu-id="6517a-138">Panoramica dell'uso della tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="6517a-138">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="6517a-139">Utilizzo degli eventi di tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="6517a-139">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="6517a-140">Utilizzo degli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="6517a-140">Using mouse events (Windows Forms .NET)</span></span>](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
