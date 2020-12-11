---
title: Come simulare gli eventi del mouse
description: Informazioni su come simulare gli eventi del mouse in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 443611163d33a266b3c49d03df13131c994b0bd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967759"
---
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a><span data-ttu-id="cd78a-103">Come simulare gli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="cd78a-103">How to simulate mouse events (Windows Forms .NET)</span></span>

<span data-ttu-id="cd78a-104">La simulazione degli eventi del mouse in Windows Forms non è altrettanto semplice come simulare gli eventi della tastiera.</span><span class="sxs-lookup"><span data-stu-id="cd78a-104">Simulating mouse events in Windows Forms isn't as straight forward as simulating keyboard events.</span></span> <span data-ttu-id="cd78a-105">Windows Forms non fornisce una classe helper per spostare il mouse e richiamare le azioni di clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="cd78a-105">Windows Forms doesn't provide a helper class to move the mouse and invoke mouse-click actions.</span></span> <span data-ttu-id="cd78a-106">L'unica opzione per controllare il mouse consiste nell'usare i metodi Windows nativi.</span><span class="sxs-lookup"><span data-stu-id="cd78a-106">The only option for controlling the mouse is to use native Windows methods.</span></span> <span data-ttu-id="cd78a-107">Se si utilizza un controllo personalizzato o un modulo, è possibile simulare un evento del mouse, ma non è possibile controllare direttamente il mouse.</span><span class="sxs-lookup"><span data-stu-id="cd78a-107">If you're working with a custom control or a form, you can simulate a mouse event, but you can't directly control the mouse.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a><span data-ttu-id="cd78a-108">Eventi</span><span class="sxs-lookup"><span data-stu-id="cd78a-108">Events</span></span>

<span data-ttu-id="cd78a-109">La maggior parte degli eventi dispone di un metodo corrispondente che li richiama, denominato nel modello di `On` seguito da `EventName` , ad esempio `OnMouseMove` .</span><span class="sxs-lookup"><span data-stu-id="cd78a-109">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnMouseMove`.</span></span> <span data-ttu-id="cd78a-110">Questa opzione è possibile solo all'interno di controlli o moduli personalizzati, perché questi metodi sono protetti e non è possibile accedervi dall'esterno del contesto del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="cd78a-110">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span> <span data-ttu-id="cd78a-111">Lo svantaggio dell'uso di un metodo, ad esempio `OnMouseMove` , è che non controlla effettivamente il mouse o interagisce con il controllo, ma genera semplicemente l'evento associato.</span><span class="sxs-lookup"><span data-stu-id="cd78a-111">The disadvantage to using a method such as `OnMouseMove` is that it doesn't actually control the mouse or interact with the control, it simply raises the associated event.</span></span> <span data-ttu-id="cd78a-112">Ad esempio, se si desidera simulare il passaggio del mouse su un elemento in un oggetto <xref:System.Windows.Forms.ListBox> `OnMouseMove` e il `ListBox` non reagisce visivamente con un elemento evidenziato sotto il cursore.</span><span class="sxs-lookup"><span data-stu-id="cd78a-112">For example, if you wanted to simulate hovering over an item in a <xref:System.Windows.Forms.ListBox>, `OnMouseMove` and the `ListBox` doesn't visually react with a highlighted item under the cursor.</span></span>

<span data-ttu-id="cd78a-113">Questi metodi protetti sono disponibili per simulare gli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="cd78a-113">These protected methods are available to simulate mouse events.</span></span>

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

<span data-ttu-id="cd78a-114">Per ulteriori informazioni su questi eventi, vedere [utilizzo degli eventi del mouse (Windows Forms .NET)](events.md)</span><span class="sxs-lookup"><span data-stu-id="cd78a-114">For more information about these events, see [Using mouse events (Windows Forms .NET)](events.md)</span></span>

## <a name="invoke-a-click"></a><span data-ttu-id="cd78a-115">Richiama un clic</span><span class="sxs-lookup"><span data-stu-id="cd78a-115">Invoke a click</span></span>

<span data-ttu-id="cd78a-116">Considerando la maggior parte dei controlli, quando si fa clic su un pulsante, ad esempio un pulsante che chiama il codice utente o la casella di controllo modifica lo stato di selezione, Windows Forms fornisce un modo semplice per attivare il clic.</span><span class="sxs-lookup"><span data-stu-id="cd78a-116">Considering most controls do something when clicked, like a button calling user code, or checkbox change its checked state, Windows Forms provides an easy way to trigger the click.</span></span> <span data-ttu-id="cd78a-117">Alcuni controlli, ad esempio ComboBox, non eseguono alcuna operazione speciale quando si fa clic e la simulazione di un clic non ha alcun effetto sul controllo.</span><span class="sxs-lookup"><span data-stu-id="cd78a-117">Some controls, such as a combobox, don't do anything special when clicked and simulating a click has no effect on the control.</span></span>

### <a name="performclick"></a><span data-ttu-id="cd78a-118">PerformClick</span><span class="sxs-lookup"><span data-stu-id="cd78a-118">PerformClick</span></span>

<span data-ttu-id="cd78a-119">L' <xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> interfaccia fornisce il <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> metodo che simula un clic sul controllo.</span><span class="sxs-lookup"><span data-stu-id="cd78a-119">The <xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> interface provides the <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> method which simulates a click on the control.</span></span> <span data-ttu-id="cd78a-120">Entrambi i <xref:System.Windows.Forms.Button?displayProperty=nameWithType> <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> controlli e implementano questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cd78a-120">Both the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> and <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> controls implement this interface.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a><span data-ttu-id="cd78a-121">InvokeClick</span><span class="sxs-lookup"><span data-stu-id="cd78a-121">InvokeClick</span></span>

<span data-ttu-id="cd78a-122">Con un form un controllo personalizzato, usare il <xref:System.Windows.Forms.Control.InvokeOnClick%2A> metodo per simulare un clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="cd78a-122">With a form a custom control, use the <xref:System.Windows.Forms.Control.InvokeOnClick%2A> method to simulate a mouse click.</span></span> <span data-ttu-id="cd78a-123">Si tratta di un metodo protetto che può essere chiamato solo dall'interno del form o da un controllo personalizzato derivato.</span><span class="sxs-lookup"><span data-stu-id="cd78a-123">This is a protected method that can only be called from within the form or a derived custom control.</span></span>

<span data-ttu-id="cd78a-124">Il codice seguente, ad esempio, fa clic su una casella di controllo da `button1` .</span><span class="sxs-lookup"><span data-stu-id="cd78a-124">For example, the following code clicks a checkbox from `button1`.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a><span data-ttu-id="cd78a-125">Usare i metodi Windows nativi</span><span class="sxs-lookup"><span data-stu-id="cd78a-125">Use native Windows methods</span></span>

<span data-ttu-id="cd78a-126">Windows fornisce metodi che è possibile chiamare per simulare movimenti del mouse e clic, ad esempio [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) e [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos) .</span><span class="sxs-lookup"><span data-stu-id="cd78a-126">Windows provides methods you can call to simulate mouse movements and clicks such as [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) and [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos).</span></span> <span data-ttu-id="cd78a-127">Nell'esempio seguente il cursore del mouse viene spostato al centro di un controllo:</span><span class="sxs-lookup"><span data-stu-id="cd78a-127">The following example moves the mouse cursor to the center of a control:</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a><span data-ttu-id="cd78a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd78a-128">See also</span></span>

- [<span data-ttu-id="cd78a-129">Panoramica dell'uso del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="cd78a-129">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="cd78a-130">Utilizzo degli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="cd78a-130">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="cd78a-131">Come distinguere tra clic e doppio clic (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="cd78a-131">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="cd78a-132">Gestire i puntatori del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="cd78a-132">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
