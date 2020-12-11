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
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a>Come simulare gli eventi del mouse (Windows Forms .NET)

La simulazione degli eventi del mouse in Windows Forms non è altrettanto semplice come simulare gli eventi della tastiera. Windows Forms non fornisce una classe helper per spostare il mouse e richiamare le azioni di clic del mouse. L'unica opzione per controllare il mouse consiste nell'usare i metodi Windows nativi. Se si utilizza un controllo personalizzato o un modulo, è possibile simulare un evento del mouse, ma non è possibile controllare direttamente il mouse.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a>Eventi

La maggior parte degli eventi dispone di un metodo corrispondente che li richiama, denominato nel modello di `On` seguito da `EventName` , ad esempio `OnMouseMove` . Questa opzione è possibile solo all'interno di controlli o moduli personalizzati, perché questi metodi sono protetti e non è possibile accedervi dall'esterno del contesto del controllo o del form. Lo svantaggio dell'uso di un metodo, ad esempio `OnMouseMove` , è che non controlla effettivamente il mouse o interagisce con il controllo, ma genera semplicemente l'evento associato. Ad esempio, se si desidera simulare il passaggio del mouse su un elemento in un oggetto <xref:System.Windows.Forms.ListBox> `OnMouseMove` e il `ListBox` non reagisce visivamente con un elemento evidenziato sotto il cursore.

Questi metodi protetti sono disponibili per simulare gli eventi del mouse.

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

Per ulteriori informazioni su questi eventi, vedere [utilizzo degli eventi del mouse (Windows Forms .NET)](events.md)

## <a name="invoke-a-click"></a>Richiama un clic

Considerando la maggior parte dei controlli, quando si fa clic su un pulsante, ad esempio un pulsante che chiama il codice utente o la casella di controllo modifica lo stato di selezione, Windows Forms fornisce un modo semplice per attivare il clic. Alcuni controlli, ad esempio ComboBox, non eseguono alcuna operazione speciale quando si fa clic e la simulazione di un clic non ha alcun effetto sul controllo.

### <a name="performclick"></a>PerformClick

L' <xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> interfaccia fornisce il <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> metodo che simula un clic sul controllo. Entrambi i <xref:System.Windows.Forms.Button?displayProperty=nameWithType> <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> controlli e implementano questa interfaccia.

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a>InvokeClick

Con un form un controllo personalizzato, usare il <xref:System.Windows.Forms.Control.InvokeOnClick%2A> metodo per simulare un clic del mouse. Si tratta di un metodo protetto che può essere chiamato solo dall'interno del form o da un controllo personalizzato derivato.

Il codice seguente, ad esempio, fa clic su una casella di controllo da `button1` .

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a>Usare i metodi Windows nativi

Windows fornisce metodi che è possibile chiamare per simulare movimenti del mouse e clic, ad esempio [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) e [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos) . Nell'esempio seguente il cursore del mouse viene spostato al centro di un controllo:

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso del mouse (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi del mouse (Windows Forms .NET)](events.md)
- [Come distinguere tra clic e doppio clic (Windows Forms .NET)](how-to-distinguish-between-clicks-and-double-clicks.md)
- [Gestire i puntatori del mouse (Windows Forms .NET)](how-to-manage-cursor-pointer.md)
