---
title: Gestisci input da tastiera a livello di form
description: Informazioni su come gestire l'input da tastiera per il Windows Forms a livello di form, prima che i messaggi raggiungano un controllo.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.openlocfilehash: 51433eeb32f73385fd74d8a236a273526c1b72ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965755"
---
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a><span data-ttu-id="13fb6-103">Come gestire i messaggi di input da tastiera nel formato (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="13fb6-103">How to handle keyboard input messages in the form (Windows Forms .NET)</span></span>

<span data-ttu-id="13fb6-104">Windows Form consente di gestire i messaggi della tastiera a livello di form, prima che i messaggi raggiungano un controllo.</span><span class="sxs-lookup"><span data-stu-id="13fb6-104">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="13fb6-105">Questo articolo illustra come eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="13fb6-105">This article shows how to accomplish this task.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a><span data-ttu-id="13fb6-106">Gestire un messaggio della tastiera</span><span class="sxs-lookup"><span data-stu-id="13fb6-106">Handle a keyboard message</span></span>

<span data-ttu-id="13fb6-107">Gestire l' <xref:System.Windows.Forms.Control.KeyPress> <xref:System.Windows.Forms.Control.KeyDown> evento o del form attivo e impostare la <xref:System.Windows.Forms.Form.KeyPreview%2A> proprietà del form su `true` .</span><span class="sxs-lookup"><span data-stu-id="13fb6-107">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the active form and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true`.</span></span> <span data-ttu-id="13fb6-108">Questa proprietà fa sì che la tastiera venga ricevuta dal form prima che raggiunga tutti i controlli del form.</span><span class="sxs-lookup"><span data-stu-id="13fb6-108">This property causes the keyboard to be received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="13fb6-109">L'esempio di codice seguente gestisce l' <xref:System.Windows.Forms.Control.KeyPress> evento rilevando tutti i tasti numerici e l'utilizzo di <kbd>1</kbd>, <kbd>4</kbd>e <kbd>7</kbd>.</span><span class="sxs-lookup"><span data-stu-id="13fb6-109">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming <kbd>1</kbd>, <kbd>4</kbd>, and <kbd>7</kbd>.</span></span>

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a><span data-ttu-id="13fb6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13fb6-110">See also</span></span>

- [<span data-ttu-id="13fb6-111">Panoramica dell'uso della tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="13fb6-111">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="13fb6-112">Utilizzo degli eventi di tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="13fb6-112">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
