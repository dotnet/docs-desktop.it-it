---
title: 'Procedura dettagliata: Specifica di voci di menu standard per un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964696"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="eb063-102">Procedura dettagliata: Specifica di voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="eb063-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="eb063-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="eb063-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="eb063-104">Questa procedura dettagliata illustra come usare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="eb063-105">Il modulo risponde anche quando un utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="eb063-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="eb063-106">In questa procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb063-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="eb063-107">Creazione di un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="eb063-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="eb063-108">Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-108">Creating a standard menu.</span></span>

- <span data-ttu-id="eb063-109">Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="eb063-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="eb063-110">Gestione della selezione delle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="eb063-110">Handling menu item selection.</span></span>

<span data-ttu-id="eb063-111">Al termine, sarà presente un modulo con un menu standard che visualizza le selezioni delle voci di menu in un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="eb063-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="eb063-112">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: specificare voci di menu standard in un modulo](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="eb063-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb063-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="eb063-113">Prerequisites</span></span>

<span data-ttu-id="eb063-114">Per completare questa procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eb063-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="eb063-115">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="eb063-115">Create the project</span></span>

1. <span data-ttu-id="eb063-116">In Visual Studio creare un progetto di applicazione Windows denominato **StandardMenuForm** (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).</span><span class="sxs-lookup"><span data-stu-id="eb063-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="eb063-117">Nella Progettazione Windows Form selezionare il modulo.</span><span class="sxs-lookup"><span data-stu-id="eb063-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="eb063-118">Creare un menu standard</span><span class="sxs-lookup"><span data-stu-id="eb063-118">Create a standard menu</span></span>

<span data-ttu-id="eb063-119">Il Progettazione Windows Form può popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con le voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="eb063-120">Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="eb063-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="eb063-121">Fare clic sul <xref:System.Windows.Forms.MenuStrip> glifo azioni di progettazione del controllo ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) e selezionare **Inserisci elementi standard**.</span><span class="sxs-lookup"><span data-stu-id="eb063-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="eb063-122">Il <xref:System.Windows.Forms.MenuStrip> controllo viene popolato con le voci di menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="eb063-123">Fare clic sulla voce di menu **file** per visualizzare le voci di menu predefinite e le icone corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="eb063-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="eb063-124">Creare un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="eb063-124">Create a StatusStrip control</span></span>

<span data-ttu-id="eb063-125">Usare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato per le applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="eb063-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="eb063-126">Nell'esempio corrente, le voci di menu selezionate dall'utente vengono visualizzate in un <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="eb063-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="eb063-127">Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="eb063-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="eb063-128">Il <xref:System.Windows.Forms.StatusStrip> controllo viene ancorato automaticamente alla fine del form.</span><span class="sxs-lookup"><span data-stu-id="eb063-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="eb063-129">Fare clic sul <xref:System.Windows.Forms.StatusStrip> pulsante a discesa del controllo e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo al <xref:System.Windows.Forms.StatusStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="eb063-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="eb063-130">Gestisci selezione elemento</span><span class="sxs-lookup"><span data-stu-id="eb063-130">Handle item selection</span></span>

<span data-ttu-id="eb063-131">Gestire l' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento per rispondere quando l'utente seleziona una voce di menu.</span><span class="sxs-lookup"><span data-stu-id="eb063-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="eb063-132">Fare clic sulla voce di menu **file** creata nella sezione Creazione di un menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="eb063-133">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="eb063-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="eb063-134">Fare doppio clic sull' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="eb063-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="eb063-135">Il Progettazione Windows Form genera un gestore eventi per l' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="eb063-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="eb063-136">Inserire il codice seguente nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="eb063-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="eb063-137">Inserire la `UpdateStatus` definizione del metodo di utilità nel form.</span><span class="sxs-lookup"><span data-stu-id="eb063-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="eb063-138">Checkpoint-testare il modulo</span><span class="sxs-lookup"><span data-stu-id="eb063-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="eb063-139">Premere **F5** per compilare ed eseguire il modulo.</span><span class="sxs-lookup"><span data-stu-id="eb063-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="eb063-140">Fare clic sulla voce di menu **file** per aprire il menu.</span><span class="sxs-lookup"><span data-stu-id="eb063-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="eb063-141">Nel menu **file** fare clic su uno degli elementi per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="eb063-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="eb063-142">Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="eb063-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb063-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eb063-143">Next steps</span></span>

<span data-ttu-id="eb063-144">In questa procedura dettagliata è stato creato un modulo con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="eb063-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="eb063-145">È possibile usare la <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molti altri scopi:</span><span class="sxs-lookup"><span data-stu-id="eb063-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="eb063-146">Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip> .</span><span class="sxs-lookup"><span data-stu-id="eb063-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="eb063-147">Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="eb063-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="eb063-148">Creare un form con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.ToolStrip> controlli di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="eb063-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="eb063-149">Per altre informazioni, vedere [procedura dettagliata: creazione di un form MDI con Unione di menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="eb063-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="eb063-150">Assegnare ai <xref:System.Windows.Forms.ToolStrip> controlli un aspetto professionale.</span><span class="sxs-lookup"><span data-stu-id="eb063-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="eb063-151">Per altre informazioni, vedere [procedura: impostare il renderer ToolStrip per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="eb063-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb063-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb063-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="eb063-153">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="eb063-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
