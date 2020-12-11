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
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a>Come gestire i messaggi di input da tastiera nel formato (Windows Forms .NET)

Windows Form consente di gestire i messaggi della tastiera a livello di form, prima che i messaggi raggiungano un controllo. Questo articolo illustra come eseguire questa attività.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a>Gestire un messaggio della tastiera

Gestire l' <xref:System.Windows.Forms.Control.KeyPress> <xref:System.Windows.Forms.Control.KeyDown> evento o del form attivo e impostare la <xref:System.Windows.Forms.Form.KeyPreview%2A> proprietà del form su `true` . Questa proprietà fa sì che la tastiera venga ricevuta dal form prima che raggiunga tutti i controlli del form. L'esempio di codice seguente gestisce l' <xref:System.Windows.Forms.Control.KeyPress> evento rilevando tutti i tasti numerici e l'utilizzo di <kbd>1</kbd>, <kbd>4</kbd>e <kbd>7</kbd>.

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso della tastiera (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
