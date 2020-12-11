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
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a>Come modificare gli eventi del tasto tastiera (Windows Forms .NET)

Windows Forms permette di usare e modificare l'input da tastiera. L'utilizzo di una chiave fa riferimento alla gestione di una chiave all'interno di un metodo o di un gestore eventi in modo che altri metodi ed eventi successivi nella coda di messaggi non ricevano il valore della chiave. Inoltre, la modifica di una chiave fa riferimento alla modifica del valore di una chiave in modo che i metodi e i gestori di eventi più in basso nella coda di messaggi ricevano un valore di chiave diverso. Questo articolo illustra come eseguire queste attività.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a>Utilizzare una chiave

In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> su `true`.

-oppure-

In un gestore eventi <xref:System.Windows.Forms.Control.KeyDown> impostare la proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyEventArgs> su `true`.

> [!NOTE]
> L'impostazione della proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> nel gestore eventi <xref:System.Windows.Forms.Control.KeyDown> non impedisce la generazione degli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti attuale. Usare la proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> per questo scopo.

Nell'esempio seguente viene gestito l' <xref:System.Windows.Forms.Control.KeyPress> evento per utilizzare `A` i `a` tasti carattere e. Queste chiavi non possono essere digitate nella casella di testo:

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a>Modificare un tasto carattere standard

In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> sul valore del nuovo tasto carattere.

Nell'esempio seguente viene gestito l' <xref:System.Windows.Forms.Control.KeyPress> evento per modificare `A` i `a` tasti carattere e in `!` :

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a>Modificare un tasto non carattere

È possibile modificare solo le pressioni dei tasti non carattere ereditando dal controllo ed eseguendo l'override del <xref:System.Windows.Forms.Control.PreProcessMessage%2A> metodo. Quando l'input <xref:System.Windows.Forms.Message> viene inviato al controllo, viene elaborato prima degli eventi di generazione del controllo. È possibile intercettare questi messaggi per modificarli o bloccarli.

Nell'esempio di codice riportato di seguito viene illustrato come utilizzare la <xref:System.Windows.Forms.Message.WParam%2A> proprietà del <xref:System.Windows.Forms.Message> parametro per modificare il tasto premuto. Questo codice rileva una chiave da <kbd>F1</kbd> a <kbd>F10</kbd> e converte la chiave in una chiave numerica compresa tra <kbd>0</kbd> e <kbd>9</kbd> (dove <kbd>F10</kbd> esegue il mapping a <kbd>0</kbd>).

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso della tastiera (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
