---
title: 'Procedura dettagliata: Creazione di un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965896"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="e2d4b-102">Procedura dettagliata: Creazione di un controllo ToolStrip professionale</span><span class="sxs-lookup"><span data-stu-id="e2d4b-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="e2d4b-103">È possibile assegnare ai controlli dell'applicazione <xref:System.Windows.Forms.ToolStrip> un aspetto e un comportamento professionali scrivendo una classe derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="e2d4b-104">In questa procedura dettagliata viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> i controlli per creare un controllo composito simile al **riquadro di spostamento** fornito da Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="e2d4b-105">In questa procedura dettagliata vengono illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2d4b-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="e2d4b-106">Creazione di un progetto libreria di controlli Windows.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="e2d4b-107">Progettazione del controllo StackView.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="e2d4b-108">Implementazione di un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="e2d4b-109">Al termine, si disporrà di un controllo client personalizzato riutilizzabile con l'aspetto professionale di un controllo Microsoft Office® XP.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="e2d4b-110">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un controllo ToolStrip professionalmente](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2d4b-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e2d4b-111">Prerequisites</span></span>

<span data-ttu-id="e2d4b-112">Per completare questa procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="e2d4b-113">Creare il progetto di libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="e2d4b-113">Create the control library project</span></span>

1. <span data-ttu-id="e2d4b-114">In Visual Studio creare un nuovo progetto di libreria di controlli Windows denominato `StackViewLibrary` .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="e2d4b-115">In **Esplora soluzioni** eliminare il controllo predefinito del progetto eliminando il file di origine denominato "UserControl1.cs" o "UserControl1. vb", a seconda del linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="e2d4b-116">Per altre informazioni, vedere [procedura: rimuovere, eliminare ed escludere elementi](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-116">For more information, see [How to: Remove, Delete, and Exclude Items](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="e2d4b-117">Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento al progetto **StackViewLibrary** .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="e2d4b-118">Assegnare al nuovo file di origine il nome di base `StackView` .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="e2d4b-119">Progettare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="e2d4b-119">Design the StackView control</span></span>

<span data-ttu-id="e2d4b-120">Il `StackView` controllo è un controllo composito con un <xref:System.Windows.Forms.ToolStrip> controllo figlio.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="e2d4b-121">Per altre informazioni sui controlli compositi, vedere [varietà di controlli personalizzati](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="e2d4b-122">Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.ToolStrip> controllo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="e2d4b-123">Nella finestra **Proprietà** impostare le proprietà del <xref:System.Windows.Forms.ToolStrip> controllo in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="e2d4b-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e2d4b-124">Property</span></span>|<span data-ttu-id="e2d4b-125">Valore</span><span class="sxs-lookup"><span data-stu-id="e2d4b-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="e2d4b-126">Nome</span><span class="sxs-lookup"><span data-stu-id="e2d4b-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="e2d4b-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="e2d4b-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="e2d4b-128">Dock</span><span class="sxs-lookup"><span data-stu-id="e2d4b-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="e2d4b-129">Carattere</span><span class="sxs-lookup"><span data-stu-id="e2d4b-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="e2d4b-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="e2d4b-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="e2d4b-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="e2d4b-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="e2d4b-132">Riempimento</span><span class="sxs-lookup"><span data-stu-id="e2d4b-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="e2d4b-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="e2d4b-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="e2d4b-134">Nella Progettazione Windows Form fare clic sul <xref:System.Windows.Forms.ToolStrip> pulsante **Aggiungi** del controllo e aggiungere un oggetto <xref:System.Windows.Forms.ToolStripButton> al `stackStrip` controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="e2d4b-135">Nella finestra **Proprietà** impostare le proprietà del <xref:System.Windows.Forms.ToolStripButton> controllo in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="e2d4b-136">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e2d4b-136">Property</span></span>|<span data-ttu-id="e2d4b-137">Valore</span><span class="sxs-lookup"><span data-stu-id="e2d4b-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="e2d4b-138">Nome</span><span class="sxs-lookup"><span data-stu-id="e2d4b-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="e2d4b-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="e2d4b-139">CheckOnClick</span></span>|<span data-ttu-id="e2d4b-140">true</span><span class="sxs-lookup"><span data-stu-id="e2d4b-140">true</span></span>|
    |<span data-ttu-id="e2d4b-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="e2d4b-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="e2d4b-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="e2d4b-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="e2d4b-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="e2d4b-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="e2d4b-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="e2d4b-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="e2d4b-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="e2d4b-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="e2d4b-146">Margin</span><span class="sxs-lookup"><span data-stu-id="e2d4b-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="e2d4b-147">Riempimento</span><span class="sxs-lookup"><span data-stu-id="e2d4b-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="e2d4b-148">Testo</span><span class="sxs-lookup"><span data-stu-id="e2d4b-148">Text</span></span>|<span data-ttu-id="e2d4b-149">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="e2d4b-149">**Mail**</span></span>|
    |<span data-ttu-id="e2d4b-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="e2d4b-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="e2d4b-151">Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="e2d4b-152">Denominare i controlli `calendarStackButton` , `contactsStackButton` e `tasksStackButton` .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="e2d4b-153">Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà su **Calendar**, **Contacts** e **Tasks** rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="e2d4b-154">Gestire eventi</span><span class="sxs-lookup"><span data-stu-id="e2d4b-154">Handle events</span></span>

<span data-ttu-id="e2d4b-155">Due eventi sono importanti per fare in `StackView` modo che il controllo si comporti correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="e2d4b-156">Gestire l' <xref:System.Windows.Forms.UserControl.Load> evento per posizionare correttamente il controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="e2d4b-157">Gestire l' <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni oggetto <xref:System.Windows.Forms.ToolStripButton> per fornire il `StackView` comportamento dello stato del controllo simile al <xref:System.Windows.Forms.RadioButton> controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="e2d4b-158">Nella Progettazione Windows Form selezionare il `StackView` controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="e2d4b-159">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="e2d4b-160">Fare doppio clic sull'evento Load per generare il `StackView_Load` gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="e2d4b-161">Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="e2d4b-162">Nella Progettazione Windows Form selezionare il `mailStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="e2d4b-163">Nella finestra **Proprietà** fare clic su **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="e2d4b-164">Fare doppio clic sull'evento click.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-164">Double-click the Click event.</span></span>

     <span data-ttu-id="e2d4b-165">Il Progettazione Windows Form genera il `mailStackButton_Click` gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="e2d4b-166">Rinominare il `mailStackButton_Click` gestore eventi in `stackButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="e2d4b-167">Per altre informazioni, vedere [rinominare un simbolo di codice refactoring](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="e2d4b-168">Inserire il codice seguente nel `stackButton_Click` gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="e2d4b-169">Nella Progettazione Windows Form selezionare il `calendarStackButton` controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="e2d4b-170">Nella finestra **Proprietà** impostare l'evento click sul `stackButton_Click` gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="e2d4b-171">Ripetere i passaggi 10 e 11 per `contactsStackButton` i `tasksStackButton` controlli e.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="e2d4b-172">Definisci icone</span><span class="sxs-lookup"><span data-stu-id="e2d4b-172">Define icons</span></span>

<span data-ttu-id="e2d4b-173">A ogni `StackView` pulsante è associata un'icona.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="e2d4b-174">Per praticità, ogni icona viene rappresentata come stringa con codifica Base64, che viene deserializzata prima <xref:System.Drawing.Bitmap> della creazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="e2d4b-175">In un ambiente di produzione i dati bitmap vengono archiviati come risorsa e le icone vengono visualizzate nel Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="e2d4b-176">Per altre informazioni, vedere [procedura: aggiungere immagini di sfondo a Windows Forms](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-176">For more information, see [How to: Add Background Images to Windows Forms](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="e2d4b-177">Nell'editor di codice inserire il codice seguente nella definizione della `StackView` classe.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="e2d4b-178">Questo codice inizializza le bitmap per le <xref:System.Windows.Forms.ToolStripButton> icone.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="e2d4b-179">Aggiungere una chiamata al `InitializeImages` metodo nel costruttore della `StackView` classe.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="e2d4b-180">Implementare un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="e2d4b-180">Implement a custom renderer</span></span>

<span data-ttu-id="e2d4b-181">È possibile personalizzare la maggior parte degli elementi del `StackView` controllo implementando una classe che deriva dalla <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="e2d4b-182">In questa procedura verrà implementata una <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che Personalizza il grip e disegna sfondi sfumatura per i <xref:System.Windows.Forms.ToolStripButton> controlli.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="e2d4b-183">Inserire il codice seguente nella `StackView` definizione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="e2d4b-184">Si tratta della definizione della `StackRenderer` classe, che esegue l'override <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> dei <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> metodi, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> per produrre un aspetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="e2d4b-185">Nel `StackView` costruttore del controllo creare una nuova istanza della `StackRenderer` classe e assegnare questa istanza alla `stackStrip` proprietà del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="e2d4b-186">Testare il controllo StackView</span><span class="sxs-lookup"><span data-stu-id="e2d4b-186">Test the StackView control</span></span>

<span data-ttu-id="e2d4b-187">Il `StackView` controllo deriva dalla <xref:System.Windows.Forms.UserControl> classe.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="e2d4b-188">Pertanto, è possibile testare il controllo con il **contenitore di test UserControl**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="e2d4b-189">Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="e2d4b-190">Premere **F5** per compilare il progetto e avviare **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="e2d4b-191">Spostare il puntatore sui pulsanti del `StackView` controllo, quindi fare clic su un pulsante per visualizzare l'aspetto dello stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2d4b-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e2d4b-192">Next steps</span></span>

<span data-ttu-id="e2d4b-193">In questa procedura dettagliata è stato creato un controllo client personalizzato riutilizzabile con l'aspetto professionale di un controllo di Office XP.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="e2d4b-194">È possibile usare la <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molti altri scopi:</span><span class="sxs-lookup"><span data-stu-id="e2d4b-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="e2d4b-195">Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip> .</span><span class="sxs-lookup"><span data-stu-id="e2d4b-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="e2d4b-196">Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="e2d4b-197">Creare un modulo con un menu standard popolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="e2d4b-198">Per ulteriori informazioni, vedere [procedura dettagliata: fornire voci di menu standard a un modulo](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="e2d4b-199">Creare un form con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.ToolStrip> controlli di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="e2d4b-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="e2d4b-200">Per altre informazioni, vedere [procedura: creare un form MDI con Unione di menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4b-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2d4b-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2d4b-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e2d4b-202">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e2d4b-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="e2d4b-203">Procedura: Specificare voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="e2d4b-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
