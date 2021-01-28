---
title: 'Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: f4fb9c6e7c48a1c6671b14ba05a63dc61195105a
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957617"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="5e1e2-102">Procedura dettagliata: serializzare raccolte di tipi standard</span><span class="sxs-lookup"><span data-stu-id="5e1e2-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="5e1e2-103">I controlli personalizzati a volte espongono una raccolta come proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="5e1e2-104">In questa procedura dettagliata viene illustrato come utilizzare la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> classe per controllare la modalità di serializzazione di una raccolta in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="5e1e2-105">L'applicazione del <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore alla proprietà della raccolta garantisce che la proprietà verrà serializzata.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="5e1e2-106">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="5e1e2-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e1e2-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5e1e2-107">Prerequisites</span></span>

<span data-ttu-id="5e1e2-108">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="5e1e2-109">Creare un controllo con una raccolta serializzabile</span><span class="sxs-lookup"><span data-stu-id="5e1e2-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="5e1e2-110">Il primo passaggio consiste nel creare un controllo con una raccolta serializzabile come proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="5e1e2-111">È possibile modificare il contenuto di questa raccolta usando l' **Editor della raccolta**, a cui è possibile accedere dalla finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="5e1e2-112">In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="5e1e2-113">Rinominare `UserControl1` con `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="5e1e2-114">Per altre informazioni, vedere [rinominare un simbolo di codice refactoring](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="5e1e2-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="5e1e2-115">Nella finestra **Proprietà** impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà su **10**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="5e1e2-116">Inserire un <xref:System.Windows.Forms.TextBox> controllo in `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="5e1e2-117">Selezionare il controllo <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="5e1e2-118">Nella finestra **Proprietà** impostare le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="5e1e2-119">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5e1e2-119">Property</span></span>|<span data-ttu-id="5e1e2-120">Modificare in</span><span class="sxs-lookup"><span data-stu-id="5e1e2-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="5e1e2-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="5e1e2-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="5e1e2-122">**Ancora**</span><span class="sxs-lookup"><span data-stu-id="5e1e2-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="5e1e2-123">**BarreScorrimento**</span><span class="sxs-lookup"><span data-stu-id="5e1e2-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="5e1e2-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="5e1e2-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="5e1e2-125">Nell' **editor di codice** dichiarare un campo di matrice di stringhe denominato `stringsValue` in `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="5e1e2-126">Definire la `Strings` proprietà nell'oggetto `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5e1e2-127">Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene utilizzato per abilitare la serializzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="5e1e2-128">Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="5e1e2-129">Trovare la proprietà **Strings** in <xref:System.Windows.Forms.PropertyGrid> del **contenitore di test UserControl**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="5e1e2-130">Selezionare la proprietà **Strings** , quindi fare clic sui puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio ](./media/visual-studio-ellipsis-button.png) ) per aprire l' **Editor della raccolta di stringhe**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="5e1e2-131">Immettere diverse stringhe nell' **Editor della raccolta di stringhe**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="5e1e2-132">Separarli premendo il tasto **invio** alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="5e1e2-133">Al termine dell'immissione delle stringhe, fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5e1e2-134">Le stringhe digitate vengono visualizzate nella <xref:System.Windows.Forms.TextBox> di `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="5e1e2-135">Serializzare una proprietà di raccolta</span><span class="sxs-lookup"><span data-stu-id="5e1e2-135">Serialize a collection property</span></span>

<span data-ttu-id="5e1e2-136">Per testare il comportamento di serializzazione del controllo, è necessario inserirlo in un form e modificare il contenuto della raccolta con l' **Editor della raccolta**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="5e1e2-137">È possibile visualizzare lo stato della raccolta serializzata esaminando un file speciale della finestra di progettazione in cui il **Progettazione Windows Form** genera il codice.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="5e1e2-138">Aggiungere un progetto di applicazione Windows alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="5e1e2-139">Assegnare al progetto il nome `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="5e1e2-140">Nella **casella degli strumenti** individuare la scheda denominata **SerializationDemoControlLib Components**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="5e1e2-141">In questa scheda si troverà `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="5e1e2-142">Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="5e1e2-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="5e1e2-143">Inserire un `SerializationDemoControl` nel form.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="5e1e2-144">Trovare la `Strings` proprietà nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="5e1e2-145">Fare clic sulla `Strings` proprietà, quindi fare clic sul pulsante con i puntini di sospensione ( ![ ...) nel pulsante finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) per aprire l' **Editor della raccolta di stringhe**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="5e1e2-146">Digitare diverse stringhe nell' **Editor della raccolta di stringhe**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="5e1e2-147">Separarli premendo **invio** alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="5e1e2-148">Al termine dell'immissione delle stringhe, fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e1e2-149">Le stringhe digitate vengono visualizzate nella <xref:System.Windows.Forms.TextBox> di `SerializationDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="5e1e2-150">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="5e1e2-151">Aprire il nodo **Form1** .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-151">Open the **Form1** node.</span></span> <span data-ttu-id="5e1e2-152">Sotto è presente un file denominato **Form1.designer.cs** o **Form1. designer. vb**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="5e1e2-153">Si tratta del file in cui il **Progettazione Windows Form** emette codice che rappresenta lo stato della fase di progettazione del form e dei relativi controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="5e1e2-154">Aprire il file nell' **editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="5e1e2-155">Aprire l'area denominata **codice generato da Progettazione Windows Form** e trovare la sezione denominata **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="5e1e2-156">Sotto questa etichetta è riportato il codice che rappresenta lo stato serializzato del controllo.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="5e1e2-157">Le stringhe digitate nel passaggio 5 vengono visualizzate in un'assegnazione alla `Strings` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="5e1e2-158">Gli esempi di codice seguenti in C# e Visual Basic mostrano codice simile a quello che si noterà se le stringhe sono state digitate "Red", "Orange" e "Yellow".</span><span class="sxs-lookup"><span data-stu-id="5e1e2-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="5e1e2-159">Nell'Editor di **codice**, modificare il valore della proprietà in <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> `Strings` <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden> .</span><span class="sxs-lookup"><span data-stu-id="5e1e2-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="5e1e2-160">Ricompilare la soluzione e ripetere i passaggi 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="5e1e2-161">In questo caso, il **Progettazione Windows Form** non emette alcuna assegnazione alla `Strings` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e1e2-162">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5e1e2-162">Next steps</span></span>

<span data-ttu-id="5e1e2-163">Quando si sa come serializzare una raccolta di tipi standard, è consigliabile integrare i controlli personalizzati in modo più approfondito nell'ambiente in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5e1e2-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="5e1e2-164">Negli argomenti seguenti viene descritto come migliorare l'integrazione della fase di progettazione dei controlli personalizzati:</span><span class="sxs-lookup"><span data-stu-id="5e1e2-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="5e1e2-165">[Architettura della fase di progettazione](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5e1e2-165">[Design-Time Architecture](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="5e1e2-166">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="5e1e2-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="5e1e2-167">[Cenni preliminari sulla serializzazione della finestra di progettazione](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5e1e2-167">[Designer Serialization Overview](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="5e1e2-168">Procedura dettagliata: creazione di un controllo Windows Form che sfrutta le funzionalità di Visual Studio Design-Time</span><span class="sxs-lookup"><span data-stu-id="5e1e2-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="5e1e2-169">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5e1e2-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="5e1e2-170">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="5e1e2-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
