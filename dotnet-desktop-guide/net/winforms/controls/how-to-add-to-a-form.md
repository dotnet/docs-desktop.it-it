---
title: Aggiungere controlli a un form
description: Informazioni su come aggiungere un controllo a un modulo in Windows Forms per .NET
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.openlocfilehash: 44a20f135eb0f1503a6e5204a33aa8dca092123f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967519"
---
# <a name="add-a-control-windows-forms-net"></a>Aggiungere un controllo (Windows Forms .NET)

La maggior parte dei moduli è progettata mediante l'aggiunta di controlli all'area del form per definire un'interfaccia utente (UI). Un *controllo* è un componente di un form usato per visualizzare informazioni o accettare l'input dell'utente.<!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

Il modo principale in cui un controllo viene aggiunto a un modulo è tramite la finestra di progettazione di Visual Studio, ma è anche possibile gestire i controlli in un modulo in fase di esecuzione tramite codice.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a>Aggiungi con la finestra di progettazione

Visual Studio USA progettazione form per progettare i moduli. È presente un riquadro controlli che elenca tutti i controlli disponibili per l'app. È possibile aggiungere controlli dal riquadro in due modi:

### <a name="add-the-control-by-double-clicking"></a>Per aggiungere il controllo, fare doppio clic su

Quando si fa doppio clic su un controllo, questo viene aggiunto automaticamente al modulo aperto corrente con le impostazioni predefinite.

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="Fare doppio clic su un controllo nella casella degli strumenti in Visual Studio per .NET Windows Forms":::

### <a name="add-the-control-by-drawing"></a>Aggiungere il controllo disegnando

Selezionare il controllo facendo clic su di esso. Nel modulo trascinare la selezione di un'area. Il controllo verrà inserito per adattarsi alle dimensioni dell'area selezionata.

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="Trascinare-selezionare e creare un controllo dalla casella degli strumenti in Visual Studio per .NET Windows Forms":::

## <a name="add-with-code"></a>Aggiungi con codice

I controlli possono essere creati e quindi aggiunti a un modulo in fase di esecuzione con la <xref:System.Windows.Forms.Control.Controls%2A> raccolta del modulo. Questa raccolta può essere utilizzata anche per rimuovere i controlli da un form.

Il codice seguente aggiunge e posiziona due controlli, un' [etichetta](xref:System.Windows.Forms.Label) e una [casella di testo](xref:System.Windows.Forms.TextBox):

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a>Vedere anche

- [Procedura: impostare il testo visualizzato da un controllo di Windows Form](how-to-set-the-display-text.md)
- [Procedura: aggiungere un collegamento alla chiave di accesso a un controllo](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
