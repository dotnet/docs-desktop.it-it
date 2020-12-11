---
title: Comportamenti del mouse di trascinamento della selezione
description: Informazioni sul funzionamento del trascinamento della selezione in Windows Forms, tra cui come eseguire il trascinamento della selezione con il mouse.
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.openlocfilehash: d434b0f0e80c610fffeea26a6fff44b43ca07fed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952530"
---
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a><span data-ttu-id="64b08-103">Panoramica sul comportamento del mouse di trascinamento della selezione (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="64b08-103">Drag-and-drop mouse behavior overview (Windows Forms .NET)</span></span>

<span data-ttu-id="64b08-104">Windows Forms include un set di metodi, eventi e classi che implementano il comportamento di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="64b08-104">Windows Forms includes a set of methods, events, and classes that implement drag-and-drop behavior.</span></span> <span data-ttu-id="64b08-105">Questo argomento fornisce una panoramica del supporto per il trascinamento della selezione in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="64b08-105">This topic provides an overview of the drag-and-drop support in Windows Forms.</span></span><!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a><span data-ttu-id="64b08-106">Eventi di trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="64b08-106">Drag-and-drop events</span></span>

<span data-ttu-id="64b08-107">Esistono due categorie di eventi in un'operazione di trascinamento della selezione: eventi che si verificano sulla destinazione corrente ed eventi che si verificano sull'origine dell'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="64b08-107">There are two categories of events in a drag and drop operation: events that occur on the current target of the drag-and-drop operation, and events that occur on the source of the drag and drop operation.</span></span> <span data-ttu-id="64b08-108">Per eseguire operazioni di trascinamento della selezione, è necessario gestire questi eventi.</span><span class="sxs-lookup"><span data-stu-id="64b08-108">To perform drag-and-drop operations, you must handle these events.</span></span> <span data-ttu-id="64b08-109">Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="64b08-109">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>

## <a name="events-on-the-current-drop-target"></a><span data-ttu-id="64b08-110">Eventi sulla destinazione di rilascio corrente</span><span class="sxs-lookup"><span data-stu-id="64b08-110">Events on the current drop target</span></span>

<span data-ttu-id="64b08-111">La tabella seguente illustra gli eventi che si verificano sulla destinazione corrente di un'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="64b08-111">The following table shows the events that occur on the current target of a drag-and-drop operation.</span></span>

| <span data-ttu-id="64b08-112">Evento del mouse</span><span class="sxs-lookup"><span data-stu-id="64b08-112">Mouse Event</span></span>                                   | <span data-ttu-id="64b08-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64b08-113">Description</span></span>                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | <span data-ttu-id="64b08-114">Questo evento si verifica quando un oggetto viene trascinato all'interno dei limiti del controllo.</span><span class="sxs-lookup"><span data-stu-id="64b08-114">This event occurs when an object is dragged into the control's bounds.</span></span> <span data-ttu-id="64b08-115">Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-115">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                              |
| <xref:System.Windows.Forms.Control.DragOver>  | <span data-ttu-id="64b08-116">Questo evento si verifica quando un oggetto viene trascinato mentre il puntatore del mouse è all'interno dei limiti del controllo.</span><span class="sxs-lookup"><span data-stu-id="64b08-116">This event occurs when an object is dragged while the mouse pointer is within the control's bounds.</span></span> <span data-ttu-id="64b08-117">Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-117">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span> |
| <xref:System.Windows.Forms.Control.DragDrop>  | <span data-ttu-id="64b08-118">Questo evento si verifica quando viene completata un'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="64b08-118">This event occurs when a drag-and-drop operation is completed.</span></span> <span data-ttu-id="64b08-119">Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-119">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | <span data-ttu-id="64b08-120">Questo evento si verifica quando un oggetto viene trascinato all'esterno dei limiti del controllo.</span><span class="sxs-lookup"><span data-stu-id="64b08-120">This event occurs when an object is dragged out of the control's bounds.</span></span> <span data-ttu-id="64b08-121">Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-121">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                              |

<span data-ttu-id="64b08-122">La classe <xref:System.Windows.Forms.DragEventArgs> fornisce la posizione del puntatore del mouse, lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, i dati trascinati e i valori dell'enumerazione <xref:System.Windows.Forms.DragDropEffects> che specificano le operazioni consentite dall'origine dell'evento di trascinamento e l'effetto del rilascio sulla destinazione per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="64b08-122">The <xref:System.Windows.Forms.DragEventArgs> class provides the location of the mouse pointer, the current state of the mouse buttons and modifier keys of the keyboard, the data being dragged, and <xref:System.Windows.Forms.DragDropEffects> values that specify the operations allowed by the source of the drag event and the target drop effect for the operation.</span></span>

## <a name="events-on-the-drop-source"></a><span data-ttu-id="64b08-123">Eventi nell'origine di rilascio</span><span class="sxs-lookup"><span data-stu-id="64b08-123">Events on the drop source</span></span>

<span data-ttu-id="64b08-124">La tabella seguente illustra gli eventi che si verificano sull'origine di un'operazione di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="64b08-124">The following table shows the events that occur on the source of the drag-and-drop operation.</span></span>

|<span data-ttu-id="64b08-125">Evento del mouse</span><span class="sxs-lookup"><span data-stu-id="64b08-125">Mouse Event</span></span>|<span data-ttu-id="64b08-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64b08-126">Description</span></span>|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|<span data-ttu-id="64b08-127">Questo evento si verifica durante un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="64b08-127">This event occurs during a drag operation.</span></span> <span data-ttu-id="64b08-128">Permette di fornire all'utente un'indicazione visiva dell'operazione di trascinamento della selezione in corso, ad esempio cambiando l'aspetto del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="64b08-128">It provides an opportunity to give a visual cue to the user that the drag-and-drop operation is occurring, such as changing the mouse pointer.</span></span> <span data-ttu-id="64b08-129">Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.GiveFeedbackEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-129">The handler for this event receives an argument of type <xref:System.Windows.Forms.GiveFeedbackEventArgs>.</span></span>|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|<span data-ttu-id="64b08-130">Questo evento si verifica durante un'operazione di trascinamento della selezione e consente all'origine del trascinamento di determinare se l'operazione deve essere annullata.</span><span class="sxs-lookup"><span data-stu-id="64b08-130">This event is raised during a drag-and-drop operation and enables the drag source to determine whether the drag-and-drop operation should be canceled.</span></span> <span data-ttu-id="64b08-131">Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.QueryContinueDragEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="64b08-131">The handler for this event receives an argument of type <xref:System.Windows.Forms.QueryContinueDragEventArgs>.</span></span>|

<span data-ttu-id="64b08-132">La classe <xref:System.Windows.Forms.QueryContinueDragEventArgs> fornisce lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, un valore che specifica se è stato premuto il tasto ESC e un valore dell'enumerazione <xref:System.Windows.Forms.DragAction> che è possibile impostare per specificare se l'operazione di trascinamento della selezione deve continuare.</span><span class="sxs-lookup"><span data-stu-id="64b08-132">The <xref:System.Windows.Forms.QueryContinueDragEventArgs> class provides the current state of the mouse buttons and modifier keys of the keyboard, a value specifying whether the ESC key was pressed, and a <xref:System.Windows.Forms.DragAction> value that can be set to specify whether the drag-and-drop operation should continue.</span></span>

## <a name="performing-drag-and-drop"></a><span data-ttu-id="64b08-133">Esecuzione del trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="64b08-133">Performing drag-and-drop</span></span>

<span data-ttu-id="64b08-134">Le operazioni di trascinamento della selezione coinvolgono sempre due componenti, l' **origine di trascinamento** e l' **obiettivo di rilascio**.</span><span class="sxs-lookup"><span data-stu-id="64b08-134">Drag-and-drop operations always involve two components, the **drag source** and the **drop target**.</span></span> <span data-ttu-id="64b08-135">Per avviare un'operazione di trascinamento della selezione, designare un controllo come origine e gestire l' <xref:System.Windows.Forms.Control.MouseDown> evento.</span><span class="sxs-lookup"><span data-stu-id="64b08-135">To start a drag-and-drop operation, designate a control as the source and handle the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span> <span data-ttu-id="64b08-136">Nel gestore eventi chiamare il <xref:System.Windows.DragDrop.DoDragDrop%2A> Metodo fornendo i dati associati all'eliminazione e al <xref:System.Windows.DragDropEffects> valore.</span><span class="sxs-lookup"><span data-stu-id="64b08-136">In the event handler, call the <xref:System.Windows.DragDrop.DoDragDrop%2A> method providing the data associated with the drop and the a <xref:System.Windows.DragDropEffects> value.</span></span>

<span data-ttu-id="64b08-137">Impostare la proprietà del controllo di destinazione su <xref:System.Windows.Forms.Control.AllowDrop> `true` per consentire al controllo di accettare un'operazione di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="64b08-137">Set the target control's <xref:System.Windows.Forms.Control.AllowDrop> property set to `true` to allow that control to accept a drag-and-drop operation.</span></span> <span data-ttu-id="64b08-138">La destinazione gestisce due eventi, prima un evento in risposta al trascinamento sul controllo, ad esempio <xref:System.Windows.Forms.Control.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="64b08-138">The target handles two events, first an event in response to the drag being over the control, such as <xref:System.Windows.Forms.Control.DragOver>.</span></span> <span data-ttu-id="64b08-139">E un secondo evento che rappresenta l'azione di rilascio, <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="64b08-139">And a second event which is the drop action itself, <xref:System.Windows.Forms.Control.DragDrop>.</span></span>

<span data-ttu-id="64b08-140">Nell'esempio seguente viene illustrato un trascinamento da un <xref:System.Windows.Forms.Label> controllo a un <xref:System.Windows.Forms.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="64b08-140">The following example demonstrates a drag from a <xref:System.Windows.Forms.Label> control to a <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="64b08-141">Al termine del trascinamento, `TextBox` risponde assegnando il testo dell'etichetta a se stesso.</span><span class="sxs-lookup"><span data-stu-id="64b08-141">When the drag is completed, the `TextBox` responds by assigning the label's text to itself.</span></span>

```csharp
// Initiate the drag
private void label1_MouseDown(object sender, MouseEventArgs e) =>
    DoDragDrop(((Label)sender).Text, DragDropEffects.All);

// Set the effect filter and allow the drop on this control
private void textBox1_DragOver(object sender, DragEventArgs e) =>
    e.Effect = DragDropEffects.All;

// React to the drop on this control
private void textBox1_DragDrop(object sender, DragEventArgs e) =>
    textBox1.Text = (string)e.Data.GetData(typeof(string));
```

```vb
' Initiate the drag
Private Sub Label1_MouseDown(sender As Object, e As MouseEventArgs)
    DoDragDrop(DirectCast(sender, Label).Text, DragDropEffects.All)
End Sub

' Set the effect filter and allow the drop on this control
Private Sub TextBox1_DragOver(sender As Object, e As DragEventArgs)
    e.Effect = DragDropEffects.All
End Sub

' React to the drop on this control
Private Sub TextBox1_DragDrop(sender As Object, e As DragEventArgs)
    TextBox1.Text = e.Data.GetData(GetType(String))
End Sub
```

<span data-ttu-id="64b08-142">Per ulteriori informazioni sugli effetti di trascinamento, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> .</span><span class="sxs-lookup"><span data-stu-id="64b08-142">For more information about the drag effects, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="64b08-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64b08-143">See also</span></span>

- [<span data-ttu-id="64b08-144">Panoramica dell'uso del mouse (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="64b08-144">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
