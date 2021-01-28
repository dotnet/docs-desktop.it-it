---
title: Ereditare da controlli esistenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 7d9766c1bb1812cc5978221ccec42f5eb2c8c4ff
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957721"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="26136-102">Procedura: ereditare da controlli di Windows Form esistenti</span><span class="sxs-lookup"><span data-stu-id="26136-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="26136-103">Se si desidera estendere le funzionalità di un controllo esistente, è possibile creare un controllo derivato da un controllo esistente tramite l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="26136-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="26136-104">Quando si eredita da un controllo esistente, si ereditano tutte le funzionalità e le proprietà visive di tale controllo.</span><span class="sxs-lookup"><span data-stu-id="26136-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="26136-105">Se, ad esempio, si crea un controllo che eredita da <xref:System.Windows.Forms.Button> , il nuovo controllo avrà un aspetto simile a quello di un <xref:System.Windows.Forms.Button> controllo standard.</span><span class="sxs-lookup"><span data-stu-id="26136-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="26136-106">È quindi possibile estendere o modificare la funzionalità del nuovo controllo tramite l'implementazione di metodi e proprietà personalizzati.</span><span class="sxs-lookup"><span data-stu-id="26136-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="26136-107">In alcuni controlli, è anche possibile modificare l'aspetto visivo del controllo ereditato eseguendo l'override del relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="26136-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="26136-108">Per creare un controllo ereditato</span><span class="sxs-lookup"><span data-stu-id="26136-108">To create an inherited control</span></span>

1. <span data-ttu-id="26136-109">In Visual Studio creare un nuovo progetto di **applicazione Windows Form** .</span><span class="sxs-lookup"><span data-stu-id="26136-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="26136-110">Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="26136-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="26136-111">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .</span><span class="sxs-lookup"><span data-stu-id="26136-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="26136-112">Nella finestra di dialogo **Aggiungi nuovo elemento**, fare doppio clic su **Controllo personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="26136-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="26136-113">Un nuovo controllo personalizzato viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="26136-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="26136-114">Se si usa:</span><span class="sxs-lookup"><span data-stu-id="26136-114">If you're using:</span></span>

    - <span data-ttu-id="26136-115">Visual Basic, nella parte superiore di **Esplora soluzioni**, fare clic su **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="26136-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="26136-116">Espandere CustomControl1.vb e quindi aprire Customcontrol1 nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="26136-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="26136-117">C#, aprire CustomControl1.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="26136-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="26136-118">Individuare la dichiarazione della classe, che eredita da <xref:System.Windows.Forms.Control> .</span><span class="sxs-lookup"><span data-stu-id="26136-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="26136-119">Modificare la classe di base per il controllo da cui si desidera ereditare.</span><span class="sxs-lookup"><span data-stu-id="26136-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="26136-120">Se ad esempio si vuole ereditare da <xref:System.Windows.Forms.Button> , modificare la dichiarazione della classe nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="26136-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="26136-121">Se si usa Visual Basic, salvare e chiudere CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="26136-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="26136-122">Aprire Customcontrol1.vb nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="26136-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="26136-123">Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.</span><span class="sxs-lookup"><span data-stu-id="26136-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="26136-124">Se si desidera modificare l'aspetto grafico del controllo, eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="26136-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26136-125">L'override <xref:System.Windows.Forms.Control.OnPaint%2A> di non consentirà di modificare l'aspetto di tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="26136-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="26136-126">I controlli che dispongono di tutti i relativi disegni eseguiti da Windows, ad esempio, <xref:System.Windows.Forms.TextBox> non chiamano mai <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo e pertanto non utilizzeranno mai il codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="26136-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="26136-127">Per verificare se il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è disponibile, fare riferimento alla documentazione della Guida relativa al particolare controllo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="26136-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="26136-128">Per un elenco di tutti i controlli Windows Forms vedere [Controlli da usare in Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="26136-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="26136-129">Se un controllo non è <xref:System.Windows.Forms.Control.OnPaint%2A> elencato come metodo membro, non è possibile modificarne l'aspetto eseguendo l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="26136-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="26136-130">Per altre informazioni sul disegno personalizzato, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="26136-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. <span data-ttu-id="26136-131">Salvare ed eseguire il test del controllo.</span><span class="sxs-lookup"><span data-stu-id="26136-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="26136-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="26136-132">See also</span></span>

- [<span data-ttu-id="26136-133">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="26136-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="26136-134">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="26136-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="26136-135">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="26136-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="26136-136">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="26136-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="26136-137">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26136-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [<span data-ttu-id="26136-138">Procedura dettagliata: eredità da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="26136-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
