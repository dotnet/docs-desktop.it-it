---
title: 'Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964981"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="b9c09-102">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="b9c09-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="b9c09-103">Se i componenti sono definiti da un progetto nella soluzione attualmente aperta, verranno visualizzati automaticamente nella **casella degli strumenti**, senza alcuna azione richiesta dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b9c09-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="b9c09-104">È anche possibile popolare manualmente la **casella degli strumenti** con i componenti personalizzati usando la finestra di [dialogo Scegli elementi della casella degli strumenti (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), ma la **casella degli strumenti** prende in considerazione gli elementi degli output di compilazione della soluzione con tutte le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9c09-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="b9c09-105">Implementa <xref:System.ComponentModel.IComponent> ;</span><span class="sxs-lookup"><span data-stu-id="b9c09-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="b9c09-106">Non ha <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false` ;</span><span class="sxs-lookup"><span data-stu-id="b9c09-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="b9c09-107">Non è <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false` .</span><span class="sxs-lookup"><span data-stu-id="b9c09-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="b9c09-108">La **casella degli strumenti** non segue le catene di riferimento, quindi non Visualizza gli elementi che non sono compilati da un progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9c09-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="b9c09-109">In questa procedura dettagliata viene illustrato come un componente personalizzato viene visualizzato automaticamente nella **casella degli strumenti** dopo che il componente è stato compilato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="b9c09-110">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9c09-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="b9c09-111">Creazione di un progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b9c09-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="b9c09-112">Creazione di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-112">Creating a custom component.</span></span>

- <span data-ttu-id="b9c09-113">Creazione di un'istanza di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="b9c09-114">Scaricamento e ricaricamento di un componente personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="b9c09-115">Al termine, si noterà che la **casella degli strumenti** viene popolata con un componente creato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="b9c09-116">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="b9c09-116">Create the project</span></span>

1. <span data-ttu-id="b9c09-117">In Visual Studio creare un progetto di applicazione basato su Windows denominato `ToolboxExample` (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).</span><span class="sxs-lookup"><span data-stu-id="b9c09-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="b9c09-118">Aggiungere un nuovo componente al progetto.</span><span class="sxs-lookup"><span data-stu-id="b9c09-118">Add a new component to the project.</span></span> <span data-ttu-id="b9c09-119">nominarla `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="b9c09-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="b9c09-120">Per altre informazioni, vedere [procedura: aggiungere nuovi elementi di progetto](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b9c09-120">For more information, see [How to: Add New Project Items](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="b9c09-121">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b9c09-121">Build the project.</span></span>

4. <span data-ttu-id="b9c09-122">Scegliere la voce **Opzioni** dal menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b9c09-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="b9c09-123">Fare clic su **generale** sotto l'elemento **Progettazione Windows Form** e verificare che l'opzione **AutoToolboxPopulate** sia impostata su **true**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="b9c09-124">Creare un'istanza di un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="b9c09-124">Create an instance of a custom component</span></span>

<span data-ttu-id="b9c09-125">Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel form.</span><span class="sxs-lookup"><span data-stu-id="b9c09-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="b9c09-126">Poiché la **casella degli strumenti** rappresenta automaticamente il nuovo componente, questa operazione è semplice come la creazione di qualsiasi altro componente o controllo.</span><span class="sxs-lookup"><span data-stu-id="b9c09-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="b9c09-127">Aprire il modulo del progetto nella **finestra di progettazione dei form**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="b9c09-128">Nella **casella degli strumenti** fare clic sulla nuova scheda denominata **ToolboxExample Components**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="b9c09-129">Quando si fa clic sulla scheda, viene visualizzato **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9c09-130">Per motivi di prestazioni, i componenti nell'area popolata automaticamente della **casella degli strumenti** non visualizzano bitmap personalizzate e l'oggetto <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b9c09-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="b9c09-131">Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare la finestra di dialogo **Scegli elementi della casella degli strumenti** per caricare il componente.</span><span class="sxs-lookup"><span data-stu-id="b9c09-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="b9c09-132">Trascinare il componente nel form.</span><span class="sxs-lookup"><span data-stu-id="b9c09-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="b9c09-133">Viene creata un'istanza del componente che viene aggiunta alla **barra dei componenti**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="b9c09-134">Scaricare e ricaricare un componente personalizzato</span><span class="sxs-lookup"><span data-stu-id="b9c09-134">Unload and reload a custom component</span></span>

<span data-ttu-id="b9c09-135">La **casella degli strumenti** prende in considerazione i componenti di ogni progetto caricato e, quando un progetto viene scaricato, rimuove i riferimenti ai componenti del progetto.</span><span class="sxs-lookup"><span data-stu-id="b9c09-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="b9c09-136">Scaricare il progetto dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9c09-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="b9c09-137">Per altre informazioni sullo scaricamento dei progetti, vedere [procedura: scaricare e ricaricare i progetti](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b9c09-137">For more information about unloading projects, see [How to: Unload and Reload Projects](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="b9c09-138">Se viene richiesto di salvare, scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="b9c09-139">Aggiungere un nuovo progetto di **applicazione Windows** alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9c09-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="b9c09-140">Aprire il modulo nella **finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b9c09-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="b9c09-141">La scheda **Componenti ToolboxExample** del progetto precedente non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="b9c09-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="b9c09-142">Ricaricare il `ToolboxExample` progetto.</span><span class="sxs-lookup"><span data-stu-id="b9c09-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="b9c09-143">Viene nuovamente visualizzata la scheda **componenti di ToolboxExample** .</span><span class="sxs-lookup"><span data-stu-id="b9c09-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9c09-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b9c09-144">Next steps</span></span>

<span data-ttu-id="b9c09-145">In questa procedura dettagliata viene illustrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma anche la **casella degli strumenti** prende in considerazione i controlli.</span><span class="sxs-lookup"><span data-stu-id="b9c09-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="b9c09-146">Provare a usare i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.</span><span class="sxs-lookup"><span data-stu-id="b9c09-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9c09-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9c09-147">See also</span></span>

- <span data-ttu-id="b9c09-148">[Generale, Progettazione Windows Form, finestra di dialogo Opzioni](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9c09-148">[General, Windows Forms Designer, Options Dialog Box](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="b9c09-149">[Procedura: modificare le schede della Casella degli strumenti](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9c09-149">[How to: Manipulate Toolbox Tabs](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="b9c09-150">[Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9c09-150">[Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="b9c09-151">Inserimento di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b9c09-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
