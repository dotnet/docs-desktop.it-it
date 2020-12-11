---
title: Modificare gli eventi del tasto tastiera
description: Informazioni su come intercettare una chiave premere e modificare il tasto premuto in un'applicazione Windows Forms .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.openlocfilehash: 94a003a8eb5fbffd9dbaf817a3ce95ca93a7d370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963679"
---
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a><span data-ttu-id="54f8a-103">Come modificare gli eventi del tasto tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="54f8a-103">How to modify keyboard key events (Windows Forms .NET)</span></span>

<span data-ttu-id="54f8a-104">Windows Forms permette di usare e modificare l'input da tastiera.</span><span class="sxs-lookup"><span data-stu-id="54f8a-104">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="54f8a-105">L'utilizzo di una chiave fa riferimento alla gestione di una chiave all'interno di un metodo o di un gestore eventi in modo che altri metodi ed eventi successivi nella coda di messaggi non ricevano il valore della chiave.</span><span class="sxs-lookup"><span data-stu-id="54f8a-105">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue don't receive the key value.</span></span> <span data-ttu-id="54f8a-106">Inoltre, la modifica di una chiave fa riferimento alla modifica del valore di una chiave in modo che i metodi e i gestori di eventi più in basso nella coda di messaggi ricevano un valore di chiave diverso.</span><span class="sxs-lookup"><span data-stu-id="54f8a-106">And, modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="54f8a-107">Questo articolo illustra come eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="54f8a-107">This article shows how to accomplish these tasks.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a><span data-ttu-id="54f8a-108">Utilizzare una chiave</span><span class="sxs-lookup"><span data-stu-id="54f8a-108">Consume a key</span></span>

<span data-ttu-id="54f8a-109">In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> su `true`.</span><span class="sxs-lookup"><span data-stu-id="54f8a-109">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>

<span data-ttu-id="54f8a-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="54f8a-110">-or-</span></span>

<span data-ttu-id="54f8a-111">In un gestore eventi <xref:System.Windows.Forms.Control.KeyDown> impostare la proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyEventArgs> su `true`.</span><span class="sxs-lookup"><span data-stu-id="54f8a-111">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="54f8a-112">L'impostazione della proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> nel gestore eventi <xref:System.Windows.Forms.Control.KeyDown> non impedisce la generazione degli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti attuale.</span><span class="sxs-lookup"><span data-stu-id="54f8a-112">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="54f8a-113">Usare la proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="54f8a-113">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>

<span data-ttu-id="54f8a-114">Nell'esempio seguente viene gestito l' <xref:System.Windows.Forms.Control.KeyPress> evento per utilizzare `A` i `a` tasti carattere e.</span><span class="sxs-lookup"><span data-stu-id="54f8a-114">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to consume the `A` and `a` character keys.</span></span> <span data-ttu-id="54f8a-115">Queste chiavi non possono essere digitate nella casella di testo:</span><span class="sxs-lookup"><span data-stu-id="54f8a-115">Those keys can't be typed into the text box:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a><span data-ttu-id="54f8a-116">Modificare un tasto carattere standard</span><span class="sxs-lookup"><span data-stu-id="54f8a-116">Modify a standard character key</span></span>

<span data-ttu-id="54f8a-117">In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> sul valore del nuovo tasto carattere.</span><span class="sxs-lookup"><span data-stu-id="54f8a-117">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>

<span data-ttu-id="54f8a-118">Nell'esempio seguente viene gestito l' <xref:System.Windows.Forms.Control.KeyPress> evento per modificare `A` i `a` tasti carattere e in `!` :</span><span class="sxs-lookup"><span data-stu-id="54f8a-118">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to change any `A` and `a` character keys to `!`:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a><span data-ttu-id="54f8a-119">Modificare un tasto non carattere</span><span class="sxs-lookup"><span data-stu-id="54f8a-119">Modify a non-character key</span></span>

<span data-ttu-id="54f8a-120">È possibile modificare solo le pressioni dei tasti non carattere ereditando dal controllo ed eseguendo l'override del <xref:System.Windows.Forms.Control.PreProcessMessage%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="54f8a-120">You can only modify non-character key presses by inheriting from the control and overriding the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method.</span></span> <span data-ttu-id="54f8a-121">Quando l'input <xref:System.Windows.Forms.Message> viene inviato al controllo, viene elaborato prima degli eventi di generazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="54f8a-121">As the   input <xref:System.Windows.Forms.Message> is sent to the control, it's processed before the control raising events.</span></span> <span data-ttu-id="54f8a-122">È possibile intercettare questi messaggi per modificarli o bloccarli.</span><span class="sxs-lookup"><span data-stu-id="54f8a-122">You can intercept these messages to modify or block them.</span></span>

<span data-ttu-id="54f8a-123">Nell'esempio di codice riportato di seguito viene illustrato come utilizzare la <xref:System.Windows.Forms.Message.WParam%2A> proprietà del <xref:System.Windows.Forms.Message> parametro per modificare il tasto premuto.</span><span class="sxs-lookup"><span data-stu-id="54f8a-123">The following code example demonstrates how to use the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to change the key pressed.</span></span> <span data-ttu-id="54f8a-124">Questo codice rileva una chiave da <kbd>F1</kbd> a <kbd>F10</kbd> e converte la chiave in una chiave numerica compresa tra <kbd>0</kbd> e <kbd>9</kbd> (dove <kbd>F10</kbd> esegue il mapping a <kbd>0</kbd>).</span><span class="sxs-lookup"><span data-stu-id="54f8a-124">This code detects a key from <kbd>F1</kbd> through <kbd>F10</kbd> and translates the key into a numeric key ranging from <kbd>0</kbd> through <kbd>9</kbd> (where <kbd>F10</kbd> maps to <kbd>0</kbd>).</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a><span data-ttu-id="54f8a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f8a-125">See also</span></span>

- [<span data-ttu-id="54f8a-126">Panoramica dell'uso della tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="54f8a-126">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="54f8a-127">Utilizzo degli eventi di tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="54f8a-127">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
