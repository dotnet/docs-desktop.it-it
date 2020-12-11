---
title: Come distinguere tra clic singolo e doppio clic
description: Vengono descritti i diversi modi per rilevare la differenza tra un solo o doppio clic con un controllo o un modulo per Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.openlocfilehash: 7b58896a85ffd16ae2637b94d58845ed7a721c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962761"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks-windows-forms-net"></a><span data-ttu-id="3cbf7-103">Come distinguere tra clic e doppio clic (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="3cbf7-103">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>

<span data-ttu-id="3cbf7-104">In genere, un singolo *clic* avvia un'azione dell'interfaccia utente e un *doppio clic* estende l'azione.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-104">Typically, a single *click* initiates a user interface action and a *double-click* extends the action.</span></span> <span data-ttu-id="3cbf7-105">Ad esempio, un solo clic consente in genere di scegliere un elemento e un doppio clic consente di modificare l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-105">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="3cbf7-106">Gli eventi Click in Windows Form, tuttavia, non si adattano facilmente a uno scenario in cui un clic e un doppio clic eseguono azioni incompatibili, perché un'azione associata all'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> viene eseguito prima dell'azione collegata all'evento <xref:System.Windows.Forms.Control.DoubleClick> o <xref:System.Windows.Forms.Control.MouseDoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-106">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="3cbf7-107">Questo argomento illustra due soluzioni a questo problema.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-107">This topic demonstrates two solutions to this problem.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="3cbf7-108">Una soluzione consiste nel gestire l'evento di doppio clic e ripristinare le azioni nella gestione dell'evento Click.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-108">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="3cbf7-109">In rare situazioni potrebbe essere necessario simulare un comportamento di clic e doppio clic gestendo l'evento <xref:System.Windows.Forms.Control.MouseDown> e usando le proprietà <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> e <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> della classe <xref:System.Windows.Forms.SystemInformation>.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-109">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="3cbf7-110">A questo punto, si misura l'intervallo trascorso tra un clic e l'altro e, se viene eseguito un secondo clic prima che venga raggiunto il valore di <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> all'interno di un rettangolo definito da <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, eseguire l'azione di doppio clic; in caso contrario, eseguire l'azione di clic.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-110">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>

## <a name="to-roll-back-a-click-action"></a><span data-ttu-id="3cbf7-111">Per eseguire il rollback di un'azione di clic</span><span class="sxs-lookup"><span data-stu-id="3cbf7-111">To roll back a click action</span></span>

<span data-ttu-id="3cbf7-112">Assicurarsi che il controllo con cui si lavora disponga del comportamento standard di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-112">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="3cbf7-113">In caso contrario, abilitare il controllo con il metodo <xref:System.Windows.Forms.Control.SetStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-113">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="3cbf7-114">Gestire l'evento di doppio clic ed eseguire il rollback dell'azione di clic, nonché dell'azione di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-114">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="3cbf7-115">L'esempio di codice seguente illustra come creare un pulsante personalizzato con doppio clic abilitato, nonché come eseguire il rollback dell'azione di clic nel codice di gestione dell'evento di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-115">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>

<span data-ttu-id="3cbf7-116">Questo esempio di codice usa un nuovo controllo Button che Abilita i doppio clic:</span><span class="sxs-lookup"><span data-stu-id="3cbf7-116">This code example uses a new button control that enables double-clicks:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/DoubleClickButton.cs" id="DoubleClickButton":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/DoubleClickButton.vb" id="DoubleClickButton":::

<span data-ttu-id="3cbf7-117">Il codice seguente illustra come un modulo modifica lo stile del bordo in base a un clic o a un doppio clic del nuovo controllo Button:</span><span class="sxs-lookup"><span data-stu-id="3cbf7-117">The following code demonstrates how a form changes the style of border based on a click or double-click of the new button control:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form1.cs" id="RollbackForm":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form1.vb" id="RollbackForm":::

## <a name="to-distinguish-between-clicks"></a><span data-ttu-id="3cbf7-118">Per distinguere i clic</span><span class="sxs-lookup"><span data-stu-id="3cbf7-118">To distinguish between clicks</span></span>

<span data-ttu-id="3cbf7-119">Gestire l' <xref:System.Windows.Forms.Control.MouseDown> evento e determinare la posizione e l'intervallo di tempo tra i clic usando la <xref:System.Windows.Forms.SystemInformation> proprietà e un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-119">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the <xref:System.Windows.Forms.SystemInformation> property and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="3cbf7-120">Eseguire l'azione appropriata a seconda che venga eseguito un clic o un doppio clic.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-120">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="3cbf7-121">Nell'esempio di codice seguente viene illustrato come procedere.</span><span class="sxs-lookup"><span data-stu-id="3cbf7-121">The following code example demonstrates how this can be done.</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form2.cs":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form2.vb":::

## <a name="see-also"></a><span data-ttu-id="3cbf7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cbf7-122">See also</span></span>

- [<span data-ttu-id="3cbf7-123">Panoramica dell'uso del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="3cbf7-123">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="3cbf7-124">Utilizzo degli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="3cbf7-124">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="3cbf7-125">Gestire i puntatori del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="3cbf7-125">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
- [<span data-ttu-id="3cbf7-126">Come simulare gli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="3cbf7-126">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control.Click?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.MouseDown?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.SetStyle%2A?displayProperty=nameWithType>
