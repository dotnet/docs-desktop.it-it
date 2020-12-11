---
title: Esercitazione su come creare una nuova app con Visual Studio
description: Seguire questa esercitazione per informazioni su come creare una nuova app Windows Forms per .NET con Visual Studio 2019.
ms.date: 10/26/2020
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: db0712aa642e54373f686fdd24a4747bf2d195e3
ms.sourcegitcommit: e8e3f6f23b5ddf9f5c4fe1ec5f6e0a8a609d49c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "97004732"
---
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a><span data-ttu-id="14939-103">Esercitazione: creare una nuova app WinForms (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="14939-103">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>

<span data-ttu-id="14939-104">In questa breve esercitazione si apprenderà come creare una nuova app Windows Forms (WinForms) con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14939-104">In this short tutorial, you'll learn how to create a new Windows Forms (WinForms) app with Visual Studio.</span></span> <span data-ttu-id="14939-105">Una volta generata l'app iniziale, si apprenderà come aggiungere controlli e come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="14939-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="14939-106">Al termine di questa esercitazione, si disporrà di una semplice app che aggiunge nomi a una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="14939-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="14939-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="14939-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="14939-108">Creare una nuova app WinForms</span><span class="sxs-lookup"><span data-stu-id="14939-108">Create a new WinForms app</span></span>
> - <span data-ttu-id="14939-109">Aggiungere controlli a un form</span><span class="sxs-lookup"><span data-stu-id="14939-109">Add controls to a form</span></span>
> - <span data-ttu-id="14939-110">Gestire gli eventi di controllo per fornire la funzionalità dell'app</span><span class="sxs-lookup"><span data-stu-id="14939-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="14939-111">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="14939-111">Run the app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14939-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="14939-112">Prerequisites</span></span>

- [<span data-ttu-id="14939-113">Visual Studio 2019 versione 16,8 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="14939-113">Visual Studio 2019 version 16.8 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - <span data-ttu-id="14939-114">Selezionare il [carico di lavoro di Visual Studio Desktop](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span><span class="sxs-lookup"><span data-stu-id="14939-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="14939-115">Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span><span class="sxs-lookup"><span data-stu-id="14939-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-winforms-app"></a><span data-ttu-id="14939-116">Creare un'app WinForms</span><span class="sxs-lookup"><span data-stu-id="14939-116">Create a WinForms app</span></span>

<span data-ttu-id="14939-117">Il primo passaggio per creare una nuova app è l'apertura di Visual Studio e la generazione dell'app da un modello.</span><span class="sxs-lookup"><span data-stu-id="14939-117">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="14939-118">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14939-118">Open Visual Studio.</span></span>
01. <span data-ttu-id="14939-119">Selezionare **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="14939-119">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Creare un nuovo progetto di Windows Forms in Visual Studio 2019 per .NET":::

01. <span data-ttu-id="14939-121">Nella casella **Cerca modelli** Digitare **WinForms**, quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="14939-121">In the **Search for templates** box, type **winforms**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="14939-122">Nell'elenco a discesa **linguaggio codice** scegliere **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="14939-122">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="14939-123">Nell'elenco modelli selezionare **Windows Forms app (.NET)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="14939-123">In the templates list, select **Windows Forms App (.NET)** and then click **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="14939-124">Non selezionare il modello **App Windows Forms (.NET _Framework_)** .</span><span class="sxs-lookup"><span data-stu-id="14939-124">Don't select the **Windows Forms App (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="Cercare il modello di Windows Forms in Visual Studio 2019 per .NET":::

01. <span data-ttu-id="14939-126">Nella finestra **Configura nuovo progetto** impostare il **nome del progetto** su **nomi** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="14939-126">In the **Configure your new project** window, set the **Project name** to **Names** and click **Create**.</span></span>

    <span data-ttu-id="14939-127">È anche possibile salvare il progetto in una cartella diversa modificando l'impostazione del **percorso** .</span><span class="sxs-lookup"><span data-stu-id="14939-127">You can also save your project to a different folder by adjusting the **Location** setting.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="Configurare un nuovo progetto di Windows Forms in Visual Studio 2019 per .NET":::

<span data-ttu-id="14939-129">Una volta generata l'app, Visual Studio dovrebbe aprire il riquadro della finestra di progettazione per il form predefinito _Form1_.</span><span class="sxs-lookup"><span data-stu-id="14939-129">Once the app is generated, Visual Studio should open the designer pane for the default form, _Form1_.</span></span> <span data-ttu-id="14939-130">Se la finestra di progettazione dei form non è visibile, fare doppio clic sul form nel riquadro **Esplora soluzioni** per aprire la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="14939-130">If the form designer isn't visible, double-click on the form in the **Solution Explorer** pane to open the designer window.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="14939-131">Parti importanti di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14939-131">Important parts of Visual Studio</span></span>

<span data-ttu-id="14939-132">Il supporto per WinForms in Visual Studio include quattro componenti importanti con cui si interagirà quando si crea un'app:</span><span class="sxs-lookup"><span data-stu-id="14939-132">Support for WinForms in Visual Studio has four important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="I componenti importanti di Visual Studio da tenere presente durante la creazione di un progetto di Windows Forms per .NET":::

01. <span data-ttu-id="14939-134">Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="14939-134">Solution Explorer</span></span>

    <span data-ttu-id="14939-135">Tutti i file di progetto, il codice, i moduli e le risorse verranno visualizzati in questo riquadro.</span><span class="sxs-lookup"><span data-stu-id="14939-135">All if your project files, code, forms, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="14939-136">Proprietà</span><span class="sxs-lookup"><span data-stu-id="14939-136">Properties</span></span>

    <span data-ttu-id="14939-137">Questo riquadro Mostra le impostazioni delle proprietà che è possibile configurare in base all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="14939-137">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="14939-138">Se, ad esempio, si seleziona un elemento da **Esplora soluzioni**, verranno visualizzate le impostazioni delle proprietà correlate al file.</span><span class="sxs-lookup"><span data-stu-id="14939-138">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="14939-139">Se si seleziona un oggetto nella **finestra di progettazione**, verranno visualizzate le impostazioni per il controllo o il form.</span><span class="sxs-lookup"><span data-stu-id="14939-139">If you select an object in the **Designer**, you'll see settings for the control or form.</span></span>

03. <span data-ttu-id="14939-140">Progettazione form</span><span class="sxs-lookup"><span data-stu-id="14939-140">Form Designer</span></span>

    <span data-ttu-id="14939-141">Si tratta della finestra di progettazione per il form.</span><span class="sxs-lookup"><span data-stu-id="14939-141">This is the designer for the form.</span></span> <span data-ttu-id="14939-142">È interattivo ed è possibile trascinare gli oggetti dalla **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="14939-142">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="14939-143">Selezionando e spostando gli elementi nella finestra di progettazione, è possibile comporre visivamente l'interfaccia utente per l'app.</span><span class="sxs-lookup"><span data-stu-id="14939-143">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

04. <span data-ttu-id="14939-144">Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="14939-144">Toolbox</span></span>

    <span data-ttu-id="14939-145">La casella degli strumenti contiene tutti i controlli che è possibile aggiungere a un modulo.</span><span class="sxs-lookup"><span data-stu-id="14939-145">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="14939-146">Per aggiungere un controllo al form corrente, fare doppio clic su un controllo o trascinare il controllo.</span><span class="sxs-lookup"><span data-stu-id="14939-146">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

## <a name="add-controls-to-the-form"></a><span data-ttu-id="14939-147">Aggiungere controlli al form</span><span class="sxs-lookup"><span data-stu-id="14939-147">Add controls to the form</span></span>

<span data-ttu-id="14939-148">Con la finestra di progettazione dei form _Form1_ aperta, utilizzare il riquadro **casella degli strumenti** per aggiungere i controlli seguenti al form:</span><span class="sxs-lookup"><span data-stu-id="14939-148">With the _Form1_ form designer open, use the **Toolbox** pane to add the following controls to the form:</span></span>

- <span data-ttu-id="14939-149">Label</span><span class="sxs-lookup"><span data-stu-id="14939-149">Label</span></span>
- <span data-ttu-id="14939-150">Pulsante</span><span class="sxs-lookup"><span data-stu-id="14939-150">Button</span></span>
- <span data-ttu-id="14939-151">ListBox</span><span class="sxs-lookup"><span data-stu-id="14939-151">Listbox</span></span>
- <span data-ttu-id="14939-152">Casella di testo</span><span class="sxs-lookup"><span data-stu-id="14939-152">Textbox</span></span>

<span data-ttu-id="14939-153">È possibile posizionare e ridimensionare i controlli in base alle impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="14939-153">You can position and size the controls according to the following settings.</span></span> <span data-ttu-id="14939-154">Spostarli visivamente in modo che corrispondano allo screenshot seguente oppure fare clic su ogni controllo e configurare le impostazioni nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="14939-154">Either visually move them to match the screenshot that follows, or click on each control and configure the settings in the **Properties** pane.</span></span> <span data-ttu-id="14939-155">È anche possibile fare clic sull'area del titolo del modulo per selezionare il modulo:</span><span class="sxs-lookup"><span data-stu-id="14939-155">You can also click on the form title area to select the form:</span></span>

| <span data-ttu-id="14939-156">Oggetto</span><span class="sxs-lookup"><span data-stu-id="14939-156">Object</span></span>      | <span data-ttu-id="14939-157">Impostazione</span><span class="sxs-lookup"><span data-stu-id="14939-157">Setting</span></span>  | <span data-ttu-id="14939-158">Valore</span><span class="sxs-lookup"><span data-stu-id="14939-158">Value</span></span>      |
|-------------|----------|------------|
| <span data-ttu-id="14939-159">**Form**</span><span class="sxs-lookup"><span data-stu-id="14939-159">**Form**</span></span>    | <span data-ttu-id="14939-160">Testo</span><span class="sxs-lookup"><span data-stu-id="14939-160">Text</span></span>     | `Names`    |
|             | <span data-ttu-id="14939-161">Dimensione</span><span class="sxs-lookup"><span data-stu-id="14939-161">Size</span></span>     | `268, 180` |
|             |          |            |
| <span data-ttu-id="14939-162">**Label**</span><span class="sxs-lookup"><span data-stu-id="14939-162">**Label**</span></span>   | <span data-ttu-id="14939-163">Percorso</span><span class="sxs-lookup"><span data-stu-id="14939-163">Location</span></span> | `12, 9`    |
|             | <span data-ttu-id="14939-164">Testo</span><span class="sxs-lookup"><span data-stu-id="14939-164">Text</span></span>     | `Names`    |
|             |          |            |
| <span data-ttu-id="14939-165">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="14939-165">**Listbox**</span></span> | <span data-ttu-id="14939-166">Nome</span><span class="sxs-lookup"><span data-stu-id="14939-166">Name</span></span>     | `lstNames` |
|             | <span data-ttu-id="14939-167">Località</span><span class="sxs-lookup"><span data-stu-id="14939-167">Location</span></span> | `12, 27`   |
|             | <span data-ttu-id="14939-168">Dimensione</span><span class="sxs-lookup"><span data-stu-id="14939-168">Size</span></span>     | `120, 94`  |
|             |          |            |
| <span data-ttu-id="14939-169">**Casella di testo**</span><span class="sxs-lookup"><span data-stu-id="14939-169">**Textbox**</span></span> | <span data-ttu-id="14939-170">Nome</span><span class="sxs-lookup"><span data-stu-id="14939-170">Name</span></span>     | `txtName`  |
|             | <span data-ttu-id="14939-171">Località</span><span class="sxs-lookup"><span data-stu-id="14939-171">Location</span></span> | `138, 26`  |
|             | <span data-ttu-id="14939-172">Dimensione</span><span class="sxs-lookup"><span data-stu-id="14939-172">Size</span></span>     | `100, 23`  |
|             |          |            |
| <span data-ttu-id="14939-173">**Button**</span><span class="sxs-lookup"><span data-stu-id="14939-173">**Button**</span></span>  | <span data-ttu-id="14939-174">Nome</span><span class="sxs-lookup"><span data-stu-id="14939-174">Name</span></span>     | `btnAdd`   |
|             | <span data-ttu-id="14939-175">Località</span><span class="sxs-lookup"><span data-stu-id="14939-175">Location</span></span> | `138, 55`  |
|             | <span data-ttu-id="14939-176">Dimensione</span><span class="sxs-lookup"><span data-stu-id="14939-176">Size</span></span>     | `100, 23`  |
|             | <span data-ttu-id="14939-177">Testo</span><span class="sxs-lookup"><span data-stu-id="14939-177">Text</span></span>     | `Add Name` |

<span data-ttu-id="14939-178">Nella finestra di progettazione dovrebbe essere presente un modulo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="14939-178">You should have a form in the designer that looks similar to the following:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Visual Studio 2019 designer con il modulo aperto per Windows Forms per .NET":::

## <a name="handle-events"></a><span data-ttu-id="14939-180">Gestire eventi</span><span class="sxs-lookup"><span data-stu-id="14939-180">Handle events</span></span>

<span data-ttu-id="14939-181">Ora che il form contiene tutti i controlli disposti, è necessario gestire gli eventi dei controlli per rispondere all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14939-181">Now that the form has all of its controls laid out, you need to handle the events of the controls to respond to user input.</span></span> <span data-ttu-id="14939-182">Con la finestra di progettazione dei form ancora aperta, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="14939-182">With the form designer still open, perform the following steps:</span></span>

01. <span data-ttu-id="14939-183">Selezionare il controllo Button sul form.</span><span class="sxs-lookup"><span data-stu-id="14939-183">Select the button control on the form.</span></span>
01. Nel riquadro **Proprietà** fare clic sull'icona eventi :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: per elencare gli eventi del pulsante.
01. <span data-ttu-id="14939-185">Individuare l'evento **Click** e fare doppio clic su di esso per generare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="14939-185">Find the **Click** event and double-click it to generate an event handler.</span></span>

    <span data-ttu-id="14939-186">Questa azione aggiunge il codice seguente al formato:</span><span class="sxs-lookup"><span data-stu-id="14939-186">This action adds the following code to the the form:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    <span data-ttu-id="14939-187">Il codice che verrà inserito in questo gestore aggiungerà il nome specificato dal `txtName` controllo TextBox al `lstNames` controllo ListBox.</span><span class="sxs-lookup"><span data-stu-id="14939-187">The code we'll put in this handler will add the name specified by the `txtName` textbox control to the `lstNames` listbox control.</span></span> <span data-ttu-id="14939-188">Tuttavia, si desidera che siano presenti due condizioni per aggiungere il nome: il nome specificato non deve essere vuoto e il nome non deve essere già esistente.</span><span class="sxs-lookup"><span data-stu-id="14939-188">However, we want there to be two conditions to adding the name: the name provided must not be blank, and the name must not already exist.</span></span>

01. <span data-ttu-id="14939-189">Il codice seguente illustra l'aggiunta di un nome al `lstNames` controllo:</span><span class="sxs-lookup"><span data-stu-id="14939-189">The following code demonstrates adding a name to the `lstNames` control:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {
        if (!string.IsNullOrWhiteSpace(txtName.Text) && !lstNames.Items.Contains(txtName.Text))
            lstNames.Items.Add(txtName.Text);
    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click
        If Not String.IsNullOrWhiteSpace(txtName.Text) And Not lstNames.Items.Contains(txtName.Text) Then
            lstNames.Items.Add(txtName.Text)
        End If
    End Sub
    ```

## <a name="run-the-app"></a><span data-ttu-id="14939-190">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="14939-190">Run the app</span></span>

<span data-ttu-id="14939-191">Ora che l'evento è stato codificato, è possibile eseguire l'app premendo il tasto <kbd>F5</kbd> o selezionando **debug**  >  **Avvia debug** dal menu.</span><span class="sxs-lookup"><span data-stu-id="14939-191">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="14939-192">Il modulo Visualizza ed è possibile immettere un nome nella casella di testo e quindi aggiungerlo facendo clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="14939-192">The form displays and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="Esecuzione di un Windows Forms per un'app .NET.":::

## <a name="next-steps"></a><span data-ttu-id="14939-194">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="14939-194">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14939-195">Altre informazioni su Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14939-195">Learn more about Windows Forms</span></span>](../overview/index.md)
