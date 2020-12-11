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
# <a name="how-to-distinguish-between-clicks-and-double-clicks-windows-forms-net"></a>Come distinguere tra clic e doppio clic (Windows Forms .NET)

In genere, un singolo *clic* avvia un'azione dell'interfaccia utente e un *doppio clic* estende l'azione. Ad esempio, un solo clic consente in genere di scegliere un elemento e un doppio clic consente di modificare l'elemento selezionato. Gli eventi Click in Windows Form, tuttavia, non si adattano facilmente a uno scenario in cui un clic e un doppio clic eseguono azioni incompatibili, perché un'azione associata all'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> viene eseguito prima dell'azione collegata all'evento <xref:System.Windows.Forms.Control.DoubleClick> o <xref:System.Windows.Forms.Control.MouseDoubleClick>. Questo argomento illustra due soluzioni a questo problema.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Una soluzione consiste nel gestire l'evento di doppio clic e ripristinare le azioni nella gestione dell'evento Click. In rare situazioni potrebbe essere necessario simulare un comportamento di clic e doppio clic gestendo l'evento <xref:System.Windows.Forms.Control.MouseDown> e usando le proprietà <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> e <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> della classe <xref:System.Windows.Forms.SystemInformation>. A questo punto, si misura l'intervallo trascorso tra un clic e l'altro e, se viene eseguito un secondo clic prima che venga raggiunto il valore di <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> all'interno di un rettangolo definito da <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, eseguire l'azione di doppio clic; in caso contrario, eseguire l'azione di clic.

## <a name="to-roll-back-a-click-action"></a>Per eseguire il rollback di un'azione di clic

Assicurarsi che il controllo con cui si lavora disponga del comportamento standard di doppio clic. In caso contrario, abilitare il controllo con il metodo <xref:System.Windows.Forms.Control.SetStyle%2A>. Gestire l'evento di doppio clic ed eseguire il rollback dell'azione di clic, nonché dell'azione di doppio clic. L'esempio di codice seguente illustra come creare un pulsante personalizzato con doppio clic abilitato, nonché come eseguire il rollback dell'azione di clic nel codice di gestione dell'evento di doppio clic.

Questo esempio di codice usa un nuovo controllo Button che Abilita i doppio clic:

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/DoubleClickButton.cs" id="DoubleClickButton":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/DoubleClickButton.vb" id="DoubleClickButton":::

Il codice seguente illustra come un modulo modifica lo stile del bordo in base a un clic o a un doppio clic del nuovo controllo Button:

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form1.cs" id="RollbackForm":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form1.vb" id="RollbackForm":::

## <a name="to-distinguish-between-clicks"></a>Per distinguere i clic

Gestire l' <xref:System.Windows.Forms.Control.MouseDown> evento e determinare la posizione e l'intervallo di tempo tra i clic usando la <xref:System.Windows.Forms.SystemInformation> proprietà e un <xref:System.Windows.Forms.Timer> componente. Eseguire l'azione appropriata a seconda che venga eseguito un clic o un doppio clic. Nell'esempio di codice seguente viene illustrato come procedere.

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form2.cs":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form2.vb":::

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso del mouse (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi del mouse (Windows Forms .NET)](events.md)
- [Gestire i puntatori del mouse (Windows Forms .NET)](how-to-manage-cursor-pointer.md)
- [Come simulare gli eventi del mouse (Windows Forms .NET)](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control.Click?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.MouseDown?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.SetStyle%2A?displayProperty=nameWithType>
