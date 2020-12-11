---
title: Sviluppare un controllo semplice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: af8ba82cc5699a4b6a12eaf921dd9f4cbf3cecd1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961873"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="e655c-102">Procedura: Sviluppare un controllo di Windows Forms semplice</span><span class="sxs-lookup"><span data-stu-id="e655c-102">How to: Develop a Simple Windows Forms Control</span></span>

<span data-ttu-id="e655c-103">Questa sezione illustra i passaggi chiave per la creazione di un controllo di Windows Form personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e655c-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="e655c-104">Il controllo semplice sviluppato in questa procedura dettagliata consente di modificare l'allineamento della relativa <xref:System.Windows.Forms.Control.Text%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e655c-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="e655c-105">Non genera o gestisce eventi.</span><span class="sxs-lookup"><span data-stu-id="e655c-105">It does not raise or handle events.</span></span>

### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="e655c-106">Per creare un controllo personalizzato semplice</span><span class="sxs-lookup"><span data-stu-id="e655c-106">To create a simple custom control</span></span>

1. <span data-ttu-id="e655c-107">Definire una classe che deriva da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e655c-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. <span data-ttu-id="e655c-108">Definire le proprietà.</span><span class="sxs-lookup"><span data-stu-id="e655c-108">Define properties.</span></span> <span data-ttu-id="e655c-109">Non è necessario definire le proprietà perché un controllo eredita molte proprietà dalla <xref:System.Windows.Forms.Control> classe, ma la maggior parte dei controlli personalizzati in genere definisce proprietà aggiuntive. Il frammento di codice seguente definisce una proprietà denominata `TextAlignment` che `FirstControl` USA per formattare la visualizzazione della <xref:System.Windows.Forms.Control.Text%2A> proprietà ereditata da <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="e655c-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="e655c-110">Per altre informazioni sulla definizione delle proprietà, vedere [Panoramica delle proprietà](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span><span class="sxs-lookup"><span data-stu-id="e655c-110">For more information about defining properties, see [Properties Overview](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     <span data-ttu-id="e655c-111">Quando si imposta una proprietà che modifica la visualizzazione del controllo, è necessario richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo per ricreare il controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <span data-ttu-id="e655c-112"><xref:System.Windows.Forms.Control.Invalidate%2A> viene definito nella classe di base <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="e655c-112"><xref:System.Windows.Forms.Control.Invalidate%2A> is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>

3. <span data-ttu-id="e655c-113">Eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo protetto ereditato da <xref:System.Windows.Forms.Control> per fornire la logica di rendering al controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="e655c-114">Se non si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> di, il controllo non sarà in grado di creare se stesso.</span><span class="sxs-lookup"><span data-stu-id="e655c-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="e655c-115">Nel frammento di codice seguente il <xref:System.Windows.Forms.Control.OnPaint%2A> Metodo Visualizza la <xref:System.Windows.Forms.Control.Text%2A> proprietà ereditata da <xref:System.Windows.Forms.Control> con l'allineamento specificato dal `alignmentValue` campo.</span><span class="sxs-lookup"><span data-stu-id="e655c-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. <span data-ttu-id="e655c-116">Specificare attributi per il controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-116">Provide attributes for your control.</span></span> <span data-ttu-id="e655c-117">Gli attributi attivano una finestra di progettazione per visualizzare correttamente il controllo e le relative proprietà ed eventi in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e655c-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="e655c-118">Il seguente frammento di codice applica attributi alla proprietà `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="e655c-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="e655c-119">In una finestra di progettazione, ad esempio Visual Studio, l' <xref:System.ComponentModel.CategoryAttribute.Category%2A> attributo (mostrato nel frammento di codice) fa sì che la proprietà venga visualizzata in una categoria logica.</span><span class="sxs-lookup"><span data-stu-id="e655c-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="e655c-120">L' <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attributo determina la visualizzazione di una stringa descrittiva nella parte inferiore della finestra **Proprietà** quando la `TextAlignment` proprietà è selezionata.</span><span class="sxs-lookup"><span data-stu-id="e655c-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="e655c-121">Per altre informazioni sugli attributi, vedere [Attributi per componenti in fase di progettazione](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="e655c-121">For more information about attributes, see [Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. <span data-ttu-id="e655c-122">(facoltativo) Specifica risorse per il controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="e655c-123">È possibile specificare una risorsa, ad esempio un'immagine bitmap, per il controllo tramite un'opzione del compilatore (`/res` per C#) per creare pacchetti di risorse con il controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="e655c-124">In fase di esecuzione, è possibile recuperare la risorsa usando i metodi della <xref:System.Resources.ResourceManager> classe.</span><span class="sxs-lookup"><span data-stu-id="e655c-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="e655c-125">Per altre informazioni sulla creazione e sull'uso di risorse, vedere [Risorse nelle applicazioni desktop](/dotnet/framework/resources/index).</span><span class="sxs-lookup"><span data-stu-id="e655c-125">For more information about creating and using resources, see the [Resources in Desktop Apps](/dotnet/framework/resources/index).</span></span>

6. <span data-ttu-id="e655c-126">Compilare e distribuire il controllo.</span><span class="sxs-lookup"><span data-stu-id="e655c-126">Compile and deploy your control.</span></span> <span data-ttu-id="e655c-127">Per compilare e distribuire `FirstControl,`, seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e655c-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>

    1. <span data-ttu-id="e655c-128">Salvare il codice dell'esempio seguente in un file di origine, ad esempio FirstControl.cs o FirstControl.vb.</span><span class="sxs-lookup"><span data-stu-id="e655c-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>

    2. <span data-ttu-id="e655c-129">Compilare il codice sorgente in un assembly e salvarlo nella directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e655c-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="e655c-130">Per questo scopo, eseguire il comando seguente dalla directory che contiene il file d'origine.</span><span class="sxs-lookup"><span data-stu-id="e655c-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         <span data-ttu-id="e655c-131">L'opzione `/t:library` indica al compilatore che l'assembly che si sta creando è una libreria e non un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e655c-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="e655c-132">L'opzione `/out` specifica il percorso e il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e655c-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="e655c-133">L'opzione `/r` specifica il nome delle assembly a cui fa riferimento il codice.</span><span class="sxs-lookup"><span data-stu-id="e655c-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="e655c-134">In questo esempio, si crea un assembly privato che può essere usato solo dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e655c-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="e655c-135">Di conseguenza, è necessario salvarlo nella directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e655c-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="e655c-136">Per altre informazioni sulla creazione di pacchetti e sulla distribuzione di un controllo, vedere [Distribuzione](/dotnet/framework/deployment/index).</span><span class="sxs-lookup"><span data-stu-id="e655c-136">For more information about packaging and deploying a control for distribution, see [Deployment](/dotnet/framework/deployment/index).</span></span>

<span data-ttu-id="e655c-137">L'esempio seguente visualizza il codice per `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="e655c-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="e655c-138">Il controllo è incluso nello spazio dei nomi `CustomWinControls`.</span><span class="sxs-lookup"><span data-stu-id="e655c-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="e655c-139">Uno spazio dei nomi specifica un raggruppamento logico di tipi correlati.</span><span class="sxs-lookup"><span data-stu-id="e655c-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="e655c-140">È possibile creare il controllo in uno spazio dei nomi nuovo o esistente.</span><span class="sxs-lookup"><span data-stu-id="e655c-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="e655c-141">In C#, la dichiarazione `using` (in Visual Basic, `Imports`) consente di accedere ai tipi da uno spazio dei nomi senza usare il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="e655c-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="e655c-142">Nell'esempio seguente la `using` dichiarazione consente al codice di accedere alla classe <xref:System.Windows.Forms.Control> da <xref:System.Windows.Forms?displayProperty=nameWithType> come semplicemente <xref:System.Windows.Forms.Control> anziché dover usare il nome completo <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e655c-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="e655c-143">Uso del controllo personalizzato in un Form</span><span class="sxs-lookup"><span data-stu-id="e655c-143">Using the Custom Control on a Form</span></span>

<span data-ttu-id="e655c-144">L'esempio seguente illustra un form semplice che usa `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="e655c-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="e655c-145">Crea tre istanze di `FirstControl`, ognuno con un valore diverso per la proprietà `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="e655c-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>

#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="e655c-146">Per compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e655c-146">To compile and run this sample</span></span>

1. <span data-ttu-id="e655c-147">Salvare il codice dell'esempio seguente in un file di origine (SimpleForm.cs o SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="e655c-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>

2. <span data-ttu-id="e655c-148">Compilare il codice sorgente in un assembly eseguibile tramite il comando seguente dalla directory che contiene il file di origine.</span><span class="sxs-lookup"><span data-stu-id="e655c-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     <span data-ttu-id="e655c-149">CustomWinControls.dll è l'assembly che contiene la classe `FirstControl` .</span><span class="sxs-lookup"><span data-stu-id="e655c-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="e655c-150">L'assembly deve essere nella stessa directory del file di origine per il form che accede all'assembly (SimpleForm.cs o SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="e655c-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>

3. <span data-ttu-id="e655c-151">Eseguire SimpleForm.exe usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e655c-151">Execute SimpleForm.exe using the following command.</span></span>

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a><span data-ttu-id="e655c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e655c-152">See also</span></span>

- [<span data-ttu-id="e655c-153">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="e655c-153">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="e655c-154">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e655c-154">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
