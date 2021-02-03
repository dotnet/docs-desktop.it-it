---
title: Esercitazione su come creare una nuova app con Visual Studio
description: Seguire questa esercitazione per informazioni su come creare una nuova app WPF per .NET con Visual Studio 2019.
ms.date: 01/18/2021
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: b2769d4901b211cf5bc7cffbe4c1bf65d26a0758
ms.sourcegitcommit: 455923e44f1e8df30a233807a54ded94ddc1cf62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "99510062"
---
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a><span data-ttu-id="4fe3a-103">Esercitazione: creare una nuova applicazione WPF (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="4fe3a-103">Tutorial: Create a new WPF app (WPF .NET)</span></span>

<span data-ttu-id="4fe3a-104">In questa breve esercitazione si apprenderà come creare una nuova app Windows Presentation Foundation (WPF) con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-104">In this short tutorial, you'll learn how to create a new Windows Presentation Foundation (WPF) app with Visual Studio.</span></span> <span data-ttu-id="4fe3a-105">Una volta generata l'app iniziale, si apprenderà come aggiungere controlli e come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="4fe3a-106">Al termine di questa esercitazione, si disporrà di una semplice app che aggiunge nomi a una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="4fe3a-107">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="4fe3a-108">Creare una nuova app WPF</span><span class="sxs-lookup"><span data-stu-id="4fe3a-108">Create a new WPF app</span></span>
> - <span data-ttu-id="4fe3a-109">Aggiungere controlli a un form</span><span class="sxs-lookup"><span data-stu-id="4fe3a-109">Add controls to a form</span></span>
> - <span data-ttu-id="4fe3a-110">Gestire gli eventi di controllo per fornire la funzionalità dell'app</span><span class="sxs-lookup"><span data-stu-id="4fe3a-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="4fe3a-111">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="4fe3a-111">Run the app</span></span>

<span data-ttu-id="4fe3a-112">Ecco un'anteprima dell'app che verrà creata durante l'esercitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-112">Here's a preview of the app you'll build while following this tutorial:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="Esercitazione sull'app di esempio per WPF completata":::

## <a name="prerequisites"></a><span data-ttu-id="4fe3a-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4fe3a-114">Prerequisites</span></span>

- [<span data-ttu-id="4fe3a-115">Visual Studio 2019 versione 16.8.4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="4fe3a-115">Visual Studio 2019 version 16.8.4 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - <span data-ttu-id="4fe3a-116">Selezionare il [carico di lavoro di Visual Studio Desktop](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span><span class="sxs-lookup"><span data-stu-id="4fe3a-116">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="4fe3a-117">Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span><span class="sxs-lookup"><span data-stu-id="4fe3a-117">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-wpf-app"></a><span data-ttu-id="4fe3a-118">Creare un'app WPF</span><span class="sxs-lookup"><span data-stu-id="4fe3a-118">Create a WPF app</span></span>

<span data-ttu-id="4fe3a-119">Il primo passaggio per creare una nuova app è l'apertura di Visual Studio e la generazione dell'app da un modello.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-119">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="4fe3a-120">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-120">Open Visual Studio.</span></span>
01. <span data-ttu-id="4fe3a-121">Selezionare **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-121">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Creare un nuovo progetto WPF in Visual Studio 2019 per .NET":::

01. <span data-ttu-id="4fe3a-123">Nella casella **Cerca modelli** Digitare **WPF**, quindi premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-123">In the **Search for templates** box, type **wpf**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="4fe3a-124">Nell'elenco a discesa **linguaggio codice** scegliere **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-124">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="4fe3a-125">Nell'elenco modelli selezionare **applicazione WPF** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-125">In the templates list, select **WPF Application** and then select **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4fe3a-126">Non selezionare il modello **applicazione WPF (.NET _Framework_)** .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-126">Don't select the **WPF Application (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search-16.8.png" alt-text="Cercare il modello WPF in Visual Studio 2019 per .NET":::

01. <span data-ttu-id="4fe3a-128">Nella finestra **Configura nuovo progetto** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-128">In the **Configure your new project** window, do the following:</span></span>

    01. <span data-ttu-id="4fe3a-129">Nella casella **nome progetto** immettere **i nomi**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-129">In the **Project name** box, enter **Names**.</span></span>
    01. <span data-ttu-id="4fe3a-130">Selezionare la casella **di controllo posiziona soluzione e progetto nella stessa directory** .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-130">Select the **Place solution and project in the same directory** check box.</span></span>
    01. <span data-ttu-id="4fe3a-131">Facoltativamente, scegliere un **percorso** diverso per salvare il codice.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-131">Optionally, choose a different **Location** to save your code.</span></span>
    01. <span data-ttu-id="4fe3a-132">Selezionare il pulsante **Crea**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-132">Select the **Create** button.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-16.8.png" alt-text="Configurare il nuovo progetto WPF in Visual Studio 2019 per .NET":::

<!-- THIS IS FOR 16.9 when it's released. Also, change the last child step of the previous step to **Next**

01. In the **Additional information** window, select **.NET 5.0 (Current)** for **Target Framework** and make sure that the **Run on .NET Framework** check box is cleared. Select the **Create** button.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Select target framework for new WPF project in Visual Studio 2019 for .NET":::
-->

<span data-ttu-id="4fe3a-134">Una volta generata l'app, Visual Studio dovrebbe aprire il riquadro finestra di progettazione XAML per la finestra predefinita, _MainWindow_.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-134">Once the app is generated, Visual Studio should open the XAML designer pane for the default window, _MainWindow_.</span></span> <span data-ttu-id="4fe3a-135">Se la finestra di progettazione non è visibile, fare doppio clic sul file _MainWindow. XAML_ nel riquadro **Esplora soluzioni** per aprire la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-135">If the designer isn't visible, double-click on the _MainWindow.xaml_ file in the **Solution Explorer** pane to open the designer.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="4fe3a-136">Parti importanti di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4fe3a-136">Important parts of Visual Studio</span></span>

<span data-ttu-id="4fe3a-137">Il supporto per WPF in Visual Studio include cinque componenti importanti con cui si interagirà quando si crea un'app:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-137">Support for WPF in Visual Studio has five important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="I componenti importanti di Visual Studio da tenere presente durante la creazione di un progetto WPF per .NET":::

01. <span data-ttu-id="4fe3a-139">Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="4fe3a-139">Solution Explorer</span></span>

    <span data-ttu-id="4fe3a-140">Tutti i file di progetto, il codice, le finestre e le risorse verranno visualizzati in questo riquadro.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-140">All of your project files, code, windows, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="4fe3a-141">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4fe3a-141">Properties</span></span>

    <span data-ttu-id="4fe3a-142">Questo riquadro Mostra le impostazioni delle proprietà che è possibile configurare in base all'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-142">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="4fe3a-143">Se, ad esempio, si seleziona un elemento da **Esplora soluzioni**, verranno visualizzate le impostazioni delle proprietà correlate al file.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-143">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="4fe3a-144">Se si seleziona un oggetto nella **finestra di progettazione**, verranno visualizzate le impostazioni per tale elemento.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-144">If you select an object in the **Designer**, you'll see settings for that item.</span></span>

03. <span data-ttu-id="4fe3a-145">Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="4fe3a-145">Toolbox</span></span>

    <span data-ttu-id="4fe3a-146">La casella degli strumenti contiene tutti i controlli che è possibile aggiungere a un modulo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-146">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="4fe3a-147">Per aggiungere un controllo al form corrente, fare doppio clic su un controllo o trascinare il controllo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-147">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

04. <span data-ttu-id="4fe3a-148">Finestra di progettazione XAML</span><span class="sxs-lookup"><span data-stu-id="4fe3a-148">XAML designer</span></span>

    <span data-ttu-id="4fe3a-149">Si tratta della finestra di progettazione per un documento XAML.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-149">This is the designer for a XAML document.</span></span> <span data-ttu-id="4fe3a-150">È interattivo ed è possibile trascinare gli oggetti dalla **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-150">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="4fe3a-151">Selezionando e spostando gli elementi nella finestra di progettazione, è possibile comporre visivamente l'interfaccia utente per l'app.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-151">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

    <span data-ttu-id="4fe3a-152">Quando sia la finestra di progettazione che l'editor sono visibili, le modifiche apportate a una vengono riflesse nell'altra.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-152">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="4fe3a-153">Quando si selezionano gli elementi nella finestra di progettazione, nel riquadro **Proprietà** vengono visualizzate le proprietà e gli attributi relativi a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-153">When you select items in the designer, the **Properties** pane displays the properties and attributes about that object.</span></span>

05. <span data-ttu-id="4fe3a-154">Editor di codice XAML</span><span class="sxs-lookup"><span data-stu-id="4fe3a-154">XAML code editor</span></span>

    <span data-ttu-id="4fe3a-155">Si tratta dell'editor di codice XAML per un documento XAML.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-155">This is the XAML code editor for a XAML document.</span></span> <span data-ttu-id="4fe3a-156">L'editor di codice XAML è un modo per creare manualmente l'interfaccia utente senza una finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-156">The XAML code editor is a way to craft your UI by hand without a designer.</span></span> <span data-ttu-id="4fe3a-157">La finestra di progettazione può dedurre i valori delle proprietà di un controllo quando il controllo viene aggiunto nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-157">The designer may infer the values of properties on a control when the control is added in the designer.</span></span> <span data-ttu-id="4fe3a-158">L'editor di codice XAML offre un maggiore controllo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-158">The XAML code editor gives you a lot more control.</span></span>

    <span data-ttu-id="4fe3a-159">Quando sia la finestra di progettazione che l'editor sono visibili, le modifiche apportate a una vengono riflesse nell'altra.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-159">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="4fe3a-160">Quando si sposta il cursore del testo nell'editor di codice, nel riquadro **Proprietà** vengono visualizzate le proprietà e gli attributi relativi a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-160">As you navigate the text caret in the code editor, the **Properties** pane displays the properties and attributes about that object.</span></span>

## <a name="target-net-50"></a><span data-ttu-id="4fe3a-161">Destinazione .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="4fe3a-161">Target .NET 5.0</span></span>

<span data-ttu-id="4fe3a-162">Dopo aver creato il progetto, modificare il Framework di destinazione in .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-162">After you create your project, change the target framework to .NET 5.0.</span></span> <span data-ttu-id="4fe3a-163">Fare doppio clic sul file di progetto _nomi_ nel **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-163">Double-click on the _Names_ project file in the **Solution Explorer**.</span></span> <span data-ttu-id="4fe3a-164">Verrà aperto il file di progetto per la modifica.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-164">This opens up the project file for editing.</span></span> <span data-ttu-id="4fe3a-165">Impostare l' `<TargetFramework>` elemento su `net5.0-windows` :</span><span class="sxs-lookup"><span data-stu-id="4fe3a-165">Set the `<TargetFramework>` element to `net5.0-windows`:</span></span>

```xml
<TargetFramework>net5.0-windows</TargetFramework>
```

<span data-ttu-id="4fe3a-166">Salvare il file di progetto e quindi chiudere la scheda dell'editor.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-166">Save the project file and then close the editor tab.</span></span>

## <a name="examine-the-xaml"></a><span data-ttu-id="4fe3a-167">Esaminare il codice XAML</span><span class="sxs-lookup"><span data-stu-id="4fe3a-167">Examine the XAML</span></span>

<span data-ttu-id="4fe3a-168">Dopo la creazione del progetto, l'editor del codice XAML è visibile con una quantità minima di codice XAML per visualizzare la finestra.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-168">After your project is created, the XAML code editor is visible with a minimal amount of XAML code to display the window.</span></span> <span data-ttu-id="4fe3a-169">Se l'editor non è aperto, fare doppio clic sull'elemento _MainWindow. XAML_ nel **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-169">If the editor isn't open, double-click the _MainWindow.xaml_ item in the **Solution Explorer**.</span></span> <span data-ttu-id="4fe3a-170">Verrà visualizzato un codice XAML simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-170">You should see XAML similar to the following:</span></span>

```xaml
<Window x:Class="Names.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Names"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>

    </Grid>
</Window>
```

<span data-ttu-id="4fe3a-171">Analizziamo questo codice XAML per comprenderlo meglio.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-171">Let's break down this XAML code to understand it better.</span></span> <span data-ttu-id="4fe3a-172">XAML è semplicemente XML che può essere elaborato dai compilatori usati da WPF.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-172">XAML is simply XML that can be processed by the compilers that WPF uses.</span></span> <span data-ttu-id="4fe3a-173">Descrive l'interfaccia utente di WPF e interagisce con il codice .NET.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-173">It describes the WPF UI and interacts with .NET code.</span></span> <span data-ttu-id="4fe3a-174">Per comprendere il codice XAML, è necessario avere almeno familiarità con le nozioni di base di XML.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-174">To understand XAML, you should, at a minimum, be familiar with the basics of XML.</span></span>

<span data-ttu-id="4fe3a-175">La radice del documento `<Window>` rappresenta il tipo di oggetto descritto dal file XAML.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-175">The document root `<Window>` represents the type of object being described by the XAML file.</span></span> <span data-ttu-id="4fe3a-176">Sono stati dichiarati otto attributi e in genere appartengono a tre categorie:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-176">There are eight attributes declared, and they generally belong to three categories:</span></span>

- <span data-ttu-id="4fe3a-177">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="4fe3a-177">Namespaces</span></span>

  <span data-ttu-id="4fe3a-178">Uno spazio dei nomi XML fornisce la struttura al codice XML, determinando che cosa è o non può essere dichiarato nel file.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-178">An XML namespace provides structure to the XML, determining what is or isn't allowed to be declared in the file.</span></span>

  <span data-ttu-id="4fe3a-179">L' `xmlns` attributo Main importa lo spazio dei nomi XML per l'intero file e, in questo caso, esegue il mapping ai tipi dichiarati da WPF.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-179">The main `xmlns` attribute imports the XML namespace for the entire file, and in this case, maps to the types declared by WPF.</span></span> <span data-ttu-id="4fe3a-180">Gli altri spazi dei nomi XML dichiarano un prefisso e importano altri tipi e oggetti per il file XAML.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-180">The other XML namespaces declare a prefix and import other types and objects for the XAML file.</span></span> <span data-ttu-id="4fe3a-181">Ad esempio, lo `xmlns:local` spazio dei nomi dichiara il `local` prefisso ed esegue il mapping agli oggetti dichiarati dal progetto, quelli dichiarati nello `Names` spazio dei nomi del codice.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-181">For example, the `xmlns:local` namespace declares the `local` prefix and maps to the objects declared by your project, the ones declared in the `Names` code namespace.</span></span>

- <span data-ttu-id="4fe3a-182">Attributo `x:Class`</span><span class="sxs-lookup"><span data-stu-id="4fe3a-182">`x:Class` attribute</span></span>

  <span data-ttu-id="4fe3a-183">Questo attributo esegue il mapping `<Window>` di al tipo definito dal codice: il file _MainWindow.XAML.cs_ o _MainWindow. XAML. vb_ , che è la `Names.MainWindow` classe.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-183">This attribute maps the `<Window>` to the type defined by your code: the _MainWindow.xaml.cs_ or _MainWindow.xaml.vb_ file, which is the `Names.MainWindow` class.</span></span>

- <span data-ttu-id="4fe3a-184">Attributo `Title`</span><span class="sxs-lookup"><span data-stu-id="4fe3a-184">`Title` attribute</span></span>

  <span data-ttu-id="4fe3a-185">Qualsiasi attributo normale dichiarato nell'oggetto XAML imposta una proprietà di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-185">Any normal attribute declared on the XAML object sets a property of that object.</span></span> <span data-ttu-id="4fe3a-186">In questo caso l' `Title` attributo imposta la `Window.Title` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-186">In this case the `Title` attribute sets the `Window.Title` property.</span></span>

## <a name="change-the-window"></a><span data-ttu-id="4fe3a-187">Modificare la finestra</span><span class="sxs-lookup"><span data-stu-id="4fe3a-187">Change the window</span></span>

<span data-ttu-id="4fe3a-188">Prima di tutto, eseguiamo il progetto e visualizziamo l'output predefinito.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-188">First, let's run the project and see the default output.</span></span> <span data-ttu-id="4fe3a-189">Si noterà che viene visualizzata una finestra, senza controlli, e un titolo **MainWindow**:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-189">You'll see that a window that pops up, without any controls, and a title of **MainWindow**:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="App WPF vuota":::

<span data-ttu-id="4fe3a-191">Per l'app di esempio, questa finestra è troppo grande e la barra del titolo non è descrittiva.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-191">For our example app, this window is too large, and the title bar isn't descriptive.</span></span> <span data-ttu-id="4fe3a-192">Modificare il titolo e le dimensioni della finestra modificando gli attributi appropriati in XAML con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-192">Change the title and size of the window by changing the appropriate attributes in the XAML to the following values:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a><span data-ttu-id="4fe3a-193">Preparare il layout</span><span class="sxs-lookup"><span data-stu-id="4fe3a-193">Prepare the layout</span></span>

<span data-ttu-id="4fe3a-194">WPF fornisce un sistema di layout potente con molti controlli di layout diversi.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-194">WPF provides a powerful layout system with many different layout controls.</span></span> <span data-ttu-id="4fe3a-195">I controlli di layout consentono di posizionare e ridimensionare i controlli figlio e possono anche eseguire tale operazione automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-195">Layout controls help place and size child controls, and can even do so automatically.</span></span> <span data-ttu-id="4fe3a-196">Il controllo di layout predefinito fornito in questo codice XAML è il `<Grid>` controllo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-196">The default layout control provided to you in this XAML is the `<Grid>` control.</span></span>

<span data-ttu-id="4fe3a-197">Il `Grid` controllo consente di definire le righe e le colonne, in modo analogo a una tabella, e di posizionare i controlli all'interno dei limiti di una combinazione di riga e colonna specifica.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-197">The `Grid` control lets you define rows and columns, much like a table, and place controls within the bounds of a specific row and column combination.</span></span> <span data-ttu-id="4fe3a-198">È possibile aggiungere un numero qualsiasi di controlli figlio o altri controlli di layout a `Grid` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-198">You can have any number of child controls or other layout controls added to the `Grid`.</span></span> <span data-ttu-id="4fe3a-199">Ad esempio, è possibile inserire un altro `Grid` controllo in una combinazione di riga e colonna specifica e il nuovo oggetto `Grid` può quindi definire più righe e colonne e avere i propri elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-199">For example, you can place another `Grid` control in a specific row and column combination, and that new `Grid` can then define more rows and columns and have its own children.</span></span>

<span data-ttu-id="4fe3a-200">Il `<Grid>` controllo definisce le righe e le colonne in cui saranno presenti i controlli.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-200">The `<Grid>` control defines rows and columns in which your controls will be.</span></span> <span data-ttu-id="4fe3a-201">In una griglia è sempre presente una sola riga e colonna dichiarata, ovvero la griglia per impostazione predefinita è una singola cella.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-201">A grid always has a single row and column declared, meaning, the grid by default is a single cell.</span></span> <span data-ttu-id="4fe3a-202">Questo non offre una maggiore flessibilità per l'inserimento di controlli.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-202">That doesn't really give you much flexibility in placing controls.</span></span>

<span data-ttu-id="4fe3a-203">Prima di aggiungere le nuove righe e colonne, aggiungere un nuovo attributo all' `<Grid>` elemento: `Margin="10"` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-203">Before we add the new rows and columns, add a new attribute to the `<Grid>` element: `Margin="10"`.</span></span> <span data-ttu-id="4fe3a-204">Questa operazione consente di ingrandire la griglia dalla finestra e renderla leggermente più gradevole.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-204">This insets the grid from the window and makes it look a little nicer.</span></span>

<span data-ttu-id="4fe3a-205">Definire quindi due righe e due colonne, dividendo la griglia in quattro celle:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-205">Next, define two rows and two columns, dividing the grid into four cells:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

<span data-ttu-id="4fe3a-206">Selezionare la griglia nell'editor del codice XAML o nella finestra di progettazione XAML. si noterà che la finestra di progettazione XAML mostra ogni riga e colonna:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-206">Select the grid in either the XAML code editor or XAML designer, you'll see that the XAML designer shows each row and column:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="Un'app WPF con il margine impostato in una griglia":::

## <a name="add-the-first-control"></a><span data-ttu-id="4fe3a-208">Aggiungere il primo controllo</span><span class="sxs-lookup"><span data-stu-id="4fe3a-208">Add the first control</span></span>

<span data-ttu-id="4fe3a-209">Ora che la griglia è stata creata, è possibile iniziare ad aggiungere controlli.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-209">Now that the grid has been created, we can start adding controls to it.</span></span> <span data-ttu-id="4fe3a-210">Innanzitutto, iniziare con il controllo Label.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-210">First, start with the label control.</span></span> <span data-ttu-id="4fe3a-211">Creare un nuovo `<Label>` elemento all'interno dell' `<Grid>` elemento, dopo le definizioni di riga e colonna, e assegnare un valore stringa `Names` :</span><span class="sxs-lookup"><span data-stu-id="4fe3a-211">Create a new `<Label>` element inside the `<Grid>` element, after the row and column definitions, and give it a string value of `Names`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

<span data-ttu-id="4fe3a-212">`<Label>Names</Label>`Definisce il contenuto `Names` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-212">The `<Label>Names</Label>` defines the content `Names`.</span></span> <span data-ttu-id="4fe3a-213">Alcuni controlli comprendono come gestire il contenuto, altri no.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-213">Some controls understand how to handle content, others don't.</span></span> <span data-ttu-id="4fe3a-214">Il contenuto di un controllo viene mappato alla `Content` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-214">The content of a control maps to the `Content` property.</span></span> <span data-ttu-id="4fe3a-215">Impostando il contenuto tramite la sintassi dell'attributo XAML, usare il formato seguente: `<Label Content="Names" />` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-215">Setting the content through XAML attribute syntax, you would use this format: `<Label Content="Names" />`.</span></span> <span data-ttu-id="4fe3a-216">Entrambe le modalità consentono di ottenere la stessa operazione, impostando il contenuto dell'etichetta in modo da visualizzare il testo `Names` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-216">Both ways accomplish the same thing, setting the content of the label to display the text `Names`.</span></span>

<span data-ttu-id="4fe3a-217">Si è verificato un problema, ma l'etichetta occupa metà della finestra perché è stata assegnata automaticamente alla prima riga e alla colonna della griglia.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-217">We have a problem though, the label takes up half the window as it was automatically assigned to the first row and column of the grid.</span></span> <span data-ttu-id="4fe3a-218">Per la prima riga, non è necessario molto spazio perché verrà usata solo tale riga per l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-218">For our first row, we don't need that much space because we're only going to use that row for the label.</span></span> <span data-ttu-id="4fe3a-219">Modificare l' `Height` attributo del primo `<RowDefinition>` da `*` a `Auto` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-219">Change the `Height` attribute of the first `<RowDefinition>` from `*` to `Auto`.</span></span> <span data-ttu-id="4fe3a-220">Il `Auto` valore Ridimensiona automaticamente la riga della griglia alla dimensione del contenuto, in questo caso il controllo Label.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-220">The `Auto` value automatically sizes the grid row to the size of its contents, in this case, the label control.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

<span data-ttu-id="4fe3a-221">Si noti che la finestra di progettazione Mostra ora l'etichetta che occupa una piccola quantità dell'altezza disponibile.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-221">Notice that the designer now shows the label occupying a small amount of the available height.</span></span> <span data-ttu-id="4fe3a-222">È ora disponibile più spazio per la riga successiva da occupare.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-222">There's now more room for the next row to occupy.</span></span> <span data-ttu-id="4fe3a-223">La maggior parte dei controlli definisce un tipo di altezza e di larghezza che devono occupare più a loro aspetto.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-223">Most controls define some sort of height and width value that they should occupy that looks best for them.</span></span> <span data-ttu-id="4fe3a-224">Nel caso del controllo Label, ha un valore di altezza che garantisce che sia possibile leggerlo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-224">In the case of the label control, it has a height value that ensures that you can read it.</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="Un'app WPF con il margine impostato in una griglia e un controllo etichetta nella prima riga":::

### <a name="control-placement"></a><span data-ttu-id="4fe3a-226">Posizionamento del controllo</span><span class="sxs-lookup"><span data-stu-id="4fe3a-226">Control placement</span></span>

<span data-ttu-id="4fe3a-227">Si esaminerà il posizionamento del controllo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-227">Let's talk about control placement.</span></span> <span data-ttu-id="4fe3a-228">L'etichetta creata nella sezione precedente è stata inserita automaticamente nella riga 0 e nella colonna 0 della griglia.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-228">The label created in the section above was automatically placed in row 0 and column 0 of the grid.</span></span> <span data-ttu-id="4fe3a-229">Il numero di righe e colonne inizia da 0 e viene incrementato di 1 per ogni nuova riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-229">The numbering for rows and columns starts at 0 and increments by 1 for each new row or column.</span></span> <span data-ttu-id="4fe3a-230">Il controllo non conosce nulla sulla griglia e il controllo non definisce alcuna proprietà per controllarne la posizione all'interno della griglia.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-230">The control doesn't know anything about the grid, and the control doesn't define any properties to control its placement within the grid.</span></span> <span data-ttu-id="4fe3a-231">Il controllo potrebbe essere stato inserito anche in un altro controllo di layout che ha un proprio set di regole che definiscono il modo in cui posizionare i controlli.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-231">The control could have even been placed within some other layout control which has its own set of rules defining how to place controls.</span></span>

<span data-ttu-id="4fe3a-232">Come si indica a un controllo di usare una riga o una colonna diversa quando il controllo non è a conoscenza della griglia?</span><span class="sxs-lookup"><span data-stu-id="4fe3a-232">How do you tell a control to use a different row or column when the control has no knowledge of the grid?</span></span> <span data-ttu-id="4fe3a-233">Proprietà associate.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-233">Attached properties!</span></span> <span data-ttu-id="4fe3a-234">La griglia sfrutta il potente sistema di proprietà fornito da WPF.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-234">The grid takes advantage of the powerful property system provided by WPF.</span></span> <span data-ttu-id="4fe3a-235">La griglia definisce le nuove proprietà che i controlli figlio possono dichiarare e utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-235">The grid defines new properties that the child controls can declare and use.</span></span> <span data-ttu-id="4fe3a-236">Le proprietà non sono effettivamente presenti nel controllo stesso, sono collegate dalla griglia quando il controllo viene aggiunto alla griglia.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-236">The properties don't actually exist on the control itself, they're attached by the grid when the control is added to the grid.</span></span>

<span data-ttu-id="4fe3a-237">La griglia definisce due proprietà per determinare la posizione di riga e colonna di un controllo figlio: `Grid.Row` e `Grid.Column` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-237">The grid defines two properties to determine the row and column placement of a child control: `Grid.Row` and `Grid.Column`.</span></span> <span data-ttu-id="4fe3a-238">Se queste proprietà vengono omesse dal controllo, è implicito che abbiano i valori predefiniti 0, quindi il controllo viene inserito in riga `0` e colonna `0` della griglia.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-238">If these properties are omitted from the control, it's implied that they have the default values of 0, so, the control is placed in row `0` and column `0` of the grid.</span></span> <span data-ttu-id="4fe3a-239">Provare a modificare la posizione del `<Label>` controllo impostando l' `Grid.Column` attributo su `1` :</span><span class="sxs-lookup"><span data-stu-id="4fe3a-239">Try changing the placement of the `<Label>` control by setting the `Grid.Column` attribute to `1`:</span></span>

```xaml
<Label Grid.Column="1">Names</Label>
```

<span data-ttu-id="4fe3a-240">Si noti che l'etichetta ora è stata spostata nella seconda colonna.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-240">Notice how your label now moved to the second column.</span></span> <span data-ttu-id="4fe3a-241">È possibile usare le `Grid.Row` `Grid.Column` proprietà associate e per inserire i controlli successivi che verranno creati.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-241">You can use the `Grid.Row` and `Grid.Column` attached properties to place the next controls we'll create.</span></span> <span data-ttu-id="4fe3a-242">Per il momento, tuttavia, ripristinare l'etichetta sulla riga 0.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-242">For now though, restore the label to row 0.</span></span>

## <a name="create-the-name-list-box"></a><span data-ttu-id="4fe3a-243">Creazione della casella di riepilogo nome</span><span class="sxs-lookup"><span data-stu-id="4fe3a-243">Create the name list box</span></span>

<span data-ttu-id="4fe3a-244">Ora che la griglia è dimensionata correttamente e l'etichetta è stata creata, aggiungere un controllo casella di riepilogo sulla riga sotto l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-244">Now that the grid is correctly sized and the label created, add a list box control on the row below the label.</span></span> <span data-ttu-id="4fe3a-245">La casella di riepilogo si troverà in righe `1` e colonne `0` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-245">The list box will be in row `1` and column `0`.</span></span> <span data-ttu-id="4fe3a-246">Verrà inoltre fornito a questo controllo il nome di `lstNames` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-246">We'll also give this control the name of `lstNames`.</span></span> <span data-ttu-id="4fe3a-247">Una volta denominato, il controllo può essere usato come riferimento nel code-behind.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-247">Once a control is named, it can be referenced in the code behind.</span></span> <span data-ttu-id="4fe3a-248">Il nome viene assegnato al controllo con l' `x:Name` attributo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-248">The name is assigned to the control with the `x:Name` attribute.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a><span data-ttu-id="4fe3a-249">Aggiungere i controlli rimanenti</span><span class="sxs-lookup"><span data-stu-id="4fe3a-249">Add the remaining controls</span></span>

<span data-ttu-id="4fe3a-250">Gli ultimi due controlli da aggiungere sono una casella di testo e un pulsante, che verranno usati dall'utente per immettere un nome da aggiungere alla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-250">The last two controls we'll add are a text box and a button, which the user will use to enter a name to add to the list box.</span></span> <span data-ttu-id="4fe3a-251">Tuttavia, anziché tentare di creare più righe e colonne per la griglia, questi controlli vengono inseriti nel `<StackPanel>` controllo del layout.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-251">However, instead of trying to create more rows and columns for the grid, we'll put these controls into the `<StackPanel>` layout control.</span></span>

<span data-ttu-id="4fe3a-252">Il pannello dello stack è diverso dalla griglia in cui vengono posizionati i controlli.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-252">The stack panel differs from the grid in how the controls are placed.</span></span> <span data-ttu-id="4fe3a-253">Quando si indica alla griglia dove si desidera che i controlli siano con le `Grid.Row` `Grid.Column` proprietà e associate, il pannello dello stack funziona automaticamente inserendo il primo controllo, quindi inserendo il controllo successivo, continuando fino a quando tutti i controlli non sono stati inseriti.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-253">While you tell the grid where you want the controls to be with the `Grid.Row` and `Grid.Column` attached properties, the stack panel works automatically by placing the first control, then placing the next control after it, continuing until all controls have been placed.</span></span> <span data-ttu-id="4fe3a-254">"Impila" ogni controllo sotto l'altro.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-254">It "stacks" each control below the other.</span></span>

<span data-ttu-id="4fe3a-255">Creare il `<StackPanel>` controllo dopo la casella di riepilogo e inserirlo nella colonna riga della griglia `1` `1` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-255">Create the `<StackPanel>` control after the list box and put it in grid row `1` column `1`.</span></span> <span data-ttu-id="4fe3a-256">Aggiungere un altro attributo denominato `Margin` con un valore `5,0,0,0` :</span><span class="sxs-lookup"><span data-stu-id="4fe3a-256">Add another attribute named `Margin` with a value of `5,0,0,0`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

<span data-ttu-id="4fe3a-257">L' `Margin` attributo è stato usato in precedenza nella griglia, ma è stato inserito un solo valore, `10` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-257">The `Margin` attribute was previously used on the grid, but we only put in a single value, `10`.</span></span> <span data-ttu-id="4fe3a-258">A questo punto è stato usato il valore `5,0,0,0` nel pannello stack.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-258">Now we've used a value of `5,0,0,0` on the stack panel.</span></span> <span data-ttu-id="4fe3a-259">Il margine è un `Thickness` tipo e può interpretare entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-259">The margin is a `Thickness` type and can interpret both values.</span></span> <span data-ttu-id="4fe3a-260">Uno spessore definisce lo spazio intorno a ogni lato di un frame rettangolare, a **sinistra**, in **alto**, a **destra**, in **basso**, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-260">A thickness defines the space around each side of a rectangular frame, **left**, **top**, **right**, **bottom**, respectively.</span></span> <span data-ttu-id="4fe3a-261">Se il valore per il margine è un singolo valore, questo valore viene utilizzato per tutti e quattro i lati.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-261">If the value for the margin is a single value, it uses that value for all four sides.</span></span>

<span data-ttu-id="4fe3a-262">Successivamente, creare un `<TextBox>` `<Button>` controllo e in `<StackPanel>` .</span><span class="sxs-lookup"><span data-stu-id="4fe3a-262">Next, create a `<TextBox>` and `<Button>` control in the `<StackPanel>`.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

<span data-ttu-id="4fe3a-263">Il layout per la finestra è completo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-263">The layout for the window is complete.</span></span> <span data-ttu-id="4fe3a-264">Tuttavia, l'app non dispone di alcuna logica per essere effettivamente funzionante.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-264">However, our app doesn't have any logic in it to actually be functional.</span></span> <span data-ttu-id="4fe3a-265">Successivamente, è necessario associare gli eventi di controllo al codice e far sì che l'app esegua effettivamente un'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-265">Next, we need to hook up the control events to code and get the app to actually do something.</span></span>

## <a name="add-code-for-the-click-event"></a><span data-ttu-id="4fe3a-266">Aggiungere il codice per l'evento click</span><span class="sxs-lookup"><span data-stu-id="4fe3a-266">Add code for the Click event</span></span>

<span data-ttu-id="4fe3a-267">Il `<Button>` creato ha un `Click` evento che viene generato quando l'utente preme il pulsante.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-267">The `<Button>` we created has a `Click` event that is raised when the user presses the button.</span></span> <span data-ttu-id="4fe3a-268">È possibile sottoscrivere questo evento e aggiungere il codice per aggiungere un nome alla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-268">You can subscribe to this event and add code to add a name to the list box.</span></span> <span data-ttu-id="4fe3a-269">Così come si imposta una proprietà su un controllo aggiungendo un attributo XAML, è possibile usare un attributo XAML per sottoscrivere un evento.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-269">Just like you set a property on a control by adding a XAML attribute, you can use a XAML attribute to subscribe to an event.</span></span> <span data-ttu-id="4fe3a-270">Impostare l' `Click` attributo su `ButtonAddName_Click`</span><span class="sxs-lookup"><span data-stu-id="4fe3a-270">Set the `Click` attribute to `ButtonAddName_Click`</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

<span data-ttu-id="4fe3a-271">A questo punto è necessario generare il codice del gestore.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-271">Now you need to generate the handler code.</span></span> <span data-ttu-id="4fe3a-272">Fare clic con il pulsante destro del mouse su `ButtonAddName_Click` e scegliere **Vai a definizione**.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-272">Right-click on `ButtonAddName_Click` and select **Go To Definition**.</span></span> <span data-ttu-id="4fe3a-273">Verrà generato un metodo nel code-behind che corrisponde al nome del gestore immesso.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-273">This will generate a method in the code behind for you that matches the handler name you've entered.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

<span data-ttu-id="4fe3a-274">Aggiungere quindi il codice seguente per eseguire questi tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="4fe3a-274">Next, add the following code to do these three steps:</span></span>

01. <span data-ttu-id="4fe3a-275">Assicurarsi che la casella di testo contenga un nome.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-275">Make sure that the text box contains a name.</span></span>
01. <span data-ttu-id="4fe3a-276">Verificare che il nome immesso nella casella di testo non esista già.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-276">Validate that the name entered in the text box doesn't already exist.</span></span>
01. <span data-ttu-id="4fe3a-277">Aggiungere il nome alla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-277">Add the name to the list box.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a><span data-ttu-id="4fe3a-278">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="4fe3a-278">Run the app</span></span>

<span data-ttu-id="4fe3a-279">Ora che l'evento è stato codificato, è possibile eseguire l'app premendo il tasto <kbd>F5</kbd> o selezionando **debug**  >  **Avvia debug** dal menu.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-279">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="4fe3a-280">Viene visualizzata la finestra ed è possibile immettere un nome nella casella di testo e quindi aggiungerlo facendo clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="4fe3a-280">The window is displayed and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="Esecuzione di un Windows Presentation Foundation (WPF) per un'app .NET.":::

## <a name="next-steps"></a><span data-ttu-id="4fe3a-282">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4fe3a-282">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4fe3a-283">Altre informazioni su Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="4fe3a-283">Learn more about Windows Presentation Foundation</span></span>](../overview/index.md)
