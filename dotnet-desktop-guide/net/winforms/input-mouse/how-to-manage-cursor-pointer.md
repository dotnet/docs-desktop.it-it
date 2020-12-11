---
title: Come gestire il puntatore del mouse
description: Informazioni su come accedere, controllare e modificare il puntatore del mouse in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.openlocfilehash: b4439c34bf7a7f41a94ce5ec5971520d9c82e469
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967762"
---
# <a name="manage-mouse-pointers-windows-forms-net"></a><span data-ttu-id="860ba-103">Gestire i puntatori del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="860ba-103">Manage mouse pointers (Windows Forms .NET)</span></span>

<span data-ttu-id="860ba-104">Il *puntatore* del mouse, a volte indicato come cursore, è una bitmap che specifica un punto di interesse sullo schermo per l'input dell'utente con il mouse.</span><span class="sxs-lookup"><span data-stu-id="860ba-104">The mouse *pointer*, which is sometimes referred to as the cursor, is a bitmap that specifies a focus point on the screen for user input with the mouse.</span></span> <span data-ttu-id="860ba-105">In questo argomento viene fornita una panoramica del puntatore del mouse in Windows Forms e vengono descritti alcuni dei modi per modificare e controllare il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="860ba-105">This topic provides an overview of the mouse pointer in Windows Forms and describes some of the ways to modify and control the mouse pointer.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessing-the-mouse-pointer"></a><span data-ttu-id="860ba-106">Accesso al puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="860ba-106">Accessing the mouse pointer</span></span>

<span data-ttu-id="860ba-107">Il puntatore del mouse è rappresentato dalla <xref:System.Windows.Forms.Cursor> classe e ognuno <xref:System.Windows.Forms.Control> presenta una <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> proprietà che specifica il puntatore per il controllo.</span><span class="sxs-lookup"><span data-stu-id="860ba-107">The mouse pointer is represented by the <xref:System.Windows.Forms.Cursor> class, and each <xref:System.Windows.Forms.Control> has a <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> property that specifies the pointer for that control.</span></span> <span data-ttu-id="860ba-108">La <xref:System.Windows.Forms.Cursor> classe contiene proprietà che descrivono il puntatore, ad esempio <xref:System.Windows.Forms.Cursor.Position%2A> le <xref:System.Windows.Forms.Cursor.HotSpot%2A> proprietà e e i metodi che possono modificare l'aspetto del puntatore, ad esempio i <xref:System.Windows.Forms.Cursor.Show%2A> <xref:System.Windows.Forms.Cursor.Hide%2A> metodi, e <xref:System.Windows.Forms.Cursor.DrawStretched%2A> .</span><span class="sxs-lookup"><span data-stu-id="860ba-108">The <xref:System.Windows.Forms.Cursor> class contains properties that describe the pointer, such as the <xref:System.Windows.Forms.Cursor.Position%2A> and <xref:System.Windows.Forms.Cursor.HotSpot%2A> properties, and methods that can modify the appearance of the pointer, such as the <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, and <xref:System.Windows.Forms.Cursor.DrawStretched%2A> methods.</span></span>

<span data-ttu-id="860ba-109">Nell'esempio seguente il cursore viene nascosto quando il cursore è posizionato su un pulsante:</span><span class="sxs-lookup"><span data-stu-id="860ba-109">The following example hides the cursor when the cursor is over a button:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="ShowHideCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="ShowHideCursor":::

## <a name="controlling-the-mouse-pointer"></a><span data-ttu-id="860ba-110">Controllo del puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="860ba-110">Controlling the mouse pointer</span></span>

<span data-ttu-id="860ba-111">In alcuni casi può essere opportuno limitare l'area in cui è possibile utilizzare il puntatore del mouse o modificare la posizione del mouse.</span><span class="sxs-lookup"><span data-stu-id="860ba-111">Sometimes you may want to limit the area in which the mouse pointer can be used or change the position the mouse.</span></span> <span data-ttu-id="860ba-112">È possibile ottenere o impostare la posizione corrente del mouse utilizzando la <xref:System.Windows.Forms.Cursor.Position%2A> proprietà dell'oggetto <xref:System.Windows.Forms.Cursor> .</span><span class="sxs-lookup"><span data-stu-id="860ba-112">You can get or set the current location of the mouse using the <xref:System.Windows.Forms.Cursor.Position%2A> property of the <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="860ba-113">Inoltre, è possibile limitare l'area in cui è possibile utilizzare il puntatore del mouse per impostare la <xref:System.Windows.Forms.Cursor.Clip%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="860ba-113">In addition, you can limit the area the mouse pointer can be used be setting the <xref:System.Windows.Forms.Cursor.Clip%2A> property.</span></span> <span data-ttu-id="860ba-114">Per impostazione predefinita, l'area di ritaglio è l'intera schermata.</span><span class="sxs-lookup"><span data-stu-id="860ba-114">The clip area, by default, is the entire screen.</span></span>

<span data-ttu-id="860ba-115">Nell'esempio seguente il puntatore del mouse viene posizionato tra due pulsanti quando si fa clic su di esso:</span><span class="sxs-lookup"><span data-stu-id="860ba-115">The following example positions the mouse pointer between two buttons when they are clicked:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="MoveCursor":::

## <a name="changing-the-mouse-pointer"></a><span data-ttu-id="860ba-116">Modifica del puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="860ba-116">Changing the mouse pointer</span></span>

<span data-ttu-id="860ba-117">La modifica del puntatore del mouse è un modo importante per fornire commenti e suggerimenti all'utente.</span><span class="sxs-lookup"><span data-stu-id="860ba-117">Changing the mouse pointer is an important way of providing feedback to the user.</span></span> <span data-ttu-id="860ba-118">Il puntatore del mouse, ad esempio, può essere modificato nei gestori degli <xref:System.Windows.Forms.Control.MouseEnter> eventi e <xref:System.Windows.Forms.Control.MouseLeave> per indicare all'utente che i calcoli sono in corso e per limitare l'interazione dell'utente nel controllo.</span><span class="sxs-lookup"><span data-stu-id="860ba-118">For example, the mouse pointer can be modified in the handlers of the <xref:System.Windows.Forms.Control.MouseEnter> and <xref:System.Windows.Forms.Control.MouseLeave> events to tell the user that computations are occurring and to limit user interaction in the control.</span></span> <span data-ttu-id="860ba-119">In alcuni casi, il puntatore del mouse verrà modificato a causa di eventi di sistema, ad esempio quando l'applicazione è in esecuzione in un'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="860ba-119">Sometimes, the mouse pointer will change because of system events, such as when your application is involved in a drag-and-drop operation.</span></span>

<span data-ttu-id="860ba-120">Il modo principale per modificare il puntatore del mouse consiste nell'impostare <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> la <xref:System.Windows.Forms.Control.DefaultCursor%2A> proprietà o di un controllo su un nuovo oggetto <xref:System.Windows.Forms.Cursor> .</span><span class="sxs-lookup"><span data-stu-id="860ba-120">The primary way to change the mouse pointer is by setting the <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.Control.DefaultCursor%2A> property of a control to a new <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="860ba-121">Per esempi relativi alla modifica del puntatore del mouse, vedere l'esempio di codice nella <xref:System.Windows.Forms.Cursor> classe.</span><span class="sxs-lookup"><span data-stu-id="860ba-121">For examples of changing the mouse pointer, see the code example in the <xref:System.Windows.Forms.Cursor> class.</span></span> <span data-ttu-id="860ba-122">Inoltre, la <xref:System.Windows.Forms.Cursors> classe espone un set di <xref:System.Windows.Forms.Cursor> oggetti per molti tipi diversi di puntatori, ad esempio un puntatore simile a una mano.</span><span class="sxs-lookup"><span data-stu-id="860ba-122">In addition, the <xref:System.Windows.Forms.Cursors> class exposes a set of <xref:System.Windows.Forms.Cursor> objects for many different types of pointers, such as a pointer that resembles a hand.</span></span>

<span data-ttu-id="860ba-123">Nell'esempio seguente il cursore del puntatore del mouse per un pulsante viene modificato in una mano:</span><span class="sxs-lookup"><span data-stu-id="860ba-123">The following example changes the cursor of the mouse pointer for a button to a hand:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="SetControlCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="SetControlCursor":::

<span data-ttu-id="860ba-124">Per visualizzare il puntatore di attesa, simile a una clessidra, ogni volta che il puntatore del mouse si trova sul controllo, utilizzare la <xref:System.Windows.Forms.Control.UseWaitCursor%2A> proprietà della <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="860ba-124">To display the wait pointer, which resembles an hourglass, whenever the mouse pointer is on the control, use the <xref:System.Windows.Forms.Control.UseWaitCursor%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="860ba-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="860ba-125">See also</span></span>

- [<span data-ttu-id="860ba-126">Panoramica dell'uso del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="860ba-126">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="860ba-127">Utilizzo degli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="860ba-127">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="860ba-128">Come distinguere tra clic e doppio clic (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="860ba-128">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="860ba-129">Come simulare gli eventi del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="860ba-129">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>
