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
# <a name="add-a-control-windows-forms-net"></a><span data-ttu-id="e5ce6-103">Aggiungere un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="e5ce6-103">Add a control (Windows Forms .NET)</span></span>

<span data-ttu-id="e5ce6-104">La maggior parte dei moduli è progettata mediante l'aggiunta di controlli all'area del form per definire un'interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="e5ce6-104">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="e5ce6-105">Un *controllo* è un componente di un form usato per visualizzare informazioni o accettare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-105">A *control* is a component on a form used to display information or accept user input.</span></span><!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

<span data-ttu-id="e5ce6-106">Il modo principale in cui un controllo viene aggiunto a un modulo è tramite la finestra di progettazione di Visual Studio, ma è anche possibile gestire i controlli in un modulo in fase di esecuzione tramite codice.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-106">The primary way a control is added to a form is through the Visual Studio Designer, but you can also manage the controls on a form at run time through code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a><span data-ttu-id="e5ce6-107">Aggiungi con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e5ce6-107">Add with Designer</span></span>

<span data-ttu-id="e5ce6-108">Visual Studio USA progettazione form per progettare i moduli.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-108">Visual Studio uses the Forms Designer to design forms.</span></span> <span data-ttu-id="e5ce6-109">È presente un riquadro controlli che elenca tutti i controlli disponibili per l'app.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-109">There is a Controls pane which lists all the controls available to your app.</span></span> <span data-ttu-id="e5ce6-110">È possibile aggiungere controlli dal riquadro in due modi:</span><span class="sxs-lookup"><span data-stu-id="e5ce6-110">You can add controls from the pane in two ways:</span></span>

### <a name="add-the-control-by-double-clicking"></a><span data-ttu-id="e5ce6-111">Per aggiungere il controllo, fare doppio clic su</span><span class="sxs-lookup"><span data-stu-id="e5ce6-111">Add the control by double-clicking</span></span>

<span data-ttu-id="e5ce6-112">Quando si fa doppio clic su un controllo, questo viene aggiunto automaticamente al modulo aperto corrente con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-112">When a control is double-clicked, it is automatically added to the current open form with default settings.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="Fare doppio clic su un controllo nella casella degli strumenti in Visual Studio per .NET Windows Forms":::

### <a name="add-the-control-by-drawing"></a><span data-ttu-id="e5ce6-114">Aggiungere il controllo disegnando</span><span class="sxs-lookup"><span data-stu-id="e5ce6-114">Add the control by drawing</span></span>

<span data-ttu-id="e5ce6-115">Selezionare il controllo facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-115">Select the control by clicking on it.</span></span> <span data-ttu-id="e5ce6-116">Nel modulo trascinare la selezione di un'area.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-116">In your form, drag-select a region.</span></span> <span data-ttu-id="e5ce6-117">Il controllo verrà inserito per adattarsi alle dimensioni dell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-117">The control will be placed to fit the size of the region you selected.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="Trascinare-selezionare e creare un controllo dalla casella degli strumenti in Visual Studio per .NET Windows Forms":::

## <a name="add-with-code"></a><span data-ttu-id="e5ce6-119">Aggiungi con codice</span><span class="sxs-lookup"><span data-stu-id="e5ce6-119">Add with code</span></span>

<span data-ttu-id="e5ce6-120">I controlli possono essere creati e quindi aggiunti a un modulo in fase di esecuzione con la <xref:System.Windows.Forms.Control.Controls%2A> raccolta del modulo.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-120">Controls can be created and then added to a form at run time with the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="e5ce6-121">Questa raccolta può essere utilizzata anche per rimuovere i controlli da un form.</span><span class="sxs-lookup"><span data-stu-id="e5ce6-121">This collection can also be used to remove controls from a form.</span></span>

<span data-ttu-id="e5ce6-122">Il codice seguente aggiunge e posiziona due controlli, un' [etichetta](xref:System.Windows.Forms.Label) e una [casella di testo](xref:System.Windows.Forms.TextBox):</span><span class="sxs-lookup"><span data-stu-id="e5ce6-122">The following code adds and positions two controls, a [Label](xref:System.Windows.Forms.Label) and a [TextBox](xref:System.Windows.Forms.TextBox):</span></span>

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a><span data-ttu-id="e5ce6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ce6-123">See also</span></span>

- [<span data-ttu-id="e5ce6-124">Procedura: impostare il testo visualizzato da un controllo di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e5ce6-124">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-display-text.md)
- [<span data-ttu-id="e5ce6-125">Procedura: aggiungere un collegamento alla chiave di accesso a un controllo</span><span class="sxs-lookup"><span data-stu-id="e5ce6-125">How to: Add an access key shortcut to a control</span></span>](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
