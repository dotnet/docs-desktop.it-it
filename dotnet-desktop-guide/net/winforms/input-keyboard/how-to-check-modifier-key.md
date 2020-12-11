---
title: Verificare il tasto di modifica premuto
description: Informazioni su come rilevare quando vengono premuti i tasti MAIUSC, ALT o CTRL in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.openlocfilehash: 7feda0f604e1cb40b34f7bf42aa122d817a5a95e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967297"
---
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a>Come verificare la pressione dei tasti di modifica (Windows Forms .NET)

Quando l'utente digita chiavi nell'applicazione, è possibile monitorare i tasti di modifica premuti, ad esempio <kbd>MAIUSC</kbd>, <kbd>ALT</kbd>e <kbd>CTRL</kbd>. Quando si preme un tasto di modifica in combinazione con altre chiavi o anche con un clic del mouse, l'applicazione può rispondere in modo appropriato. La pressione del tasto <kbd>s</kbd> , ad esempio, può causare la visualizzazione di una "s" sullo schermo. Se vengono premuti i tasti <kbd>CTRL + S</kbd> , è possibile salvare il documento corrente.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Se si gestisce l' <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> proprietà ricevuta dal gestore eventi specifica i tasti di modifica che vengono premuti. Inoltre, la <xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> proprietà specifica il carattere che è stato premuto insieme a qualsiasi tasto di modifica combinato con un operatore OR bit per bit.

Se si sta gestendo l' <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, il gestore eventi non riceve queste informazioni. Utilizzare la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà della <xref:System.Windows.Forms.Control> classe per rilevare un modificatore di chiave. In entrambi i casi, è necessario eseguire un operatore AND bit per bit del <xref:System.Windows.Forms.Keys> valore appropriato e il valore che si sta testando. L' <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni tasto di modifica, quindi è importante eseguire l'operazione bit per bit e verificare con il valore corretto.

Il tasto <kbd>MAIUSC</kbd> , ad esempio, è rappresentato dai valori chiave seguenti:

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

Il valore corretto per testare lo <kbd>spostamento</kbd> come un tasto di modifica è <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType> . Analogamente, per verificare la presenza di tasti <kbd>CTRL</kbd> e <kbd>ALT</kbd> come modificatori, è necessario usare <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> rispettivamente i <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> valori e.

## <a name="detect-modifier-key"></a>Rileva il tasto di modifica

Rilevare se viene premuto un tasto di modifica confrontando la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà e il <xref:System.Windows.Forms.Keys> valore di enumerazione con un operatore and bit per bit.

Nell'esempio di codice seguente viene illustrato come determinare se il tasto <kbd>MAIUSC</kbd> è premuto nei <xref:System.Windows.Forms.Control.KeyPress> <xref:System.Windows.Forms.Control.KeyDown> gestori eventi e.

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso della tastiera (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
