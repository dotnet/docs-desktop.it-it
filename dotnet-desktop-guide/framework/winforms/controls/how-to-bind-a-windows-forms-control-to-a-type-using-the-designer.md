---
title: Associare il controllo a un tipo utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962035"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="c35c9-102">Procedura: Associare un controllo di Windows Forms a un tipo usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="c35c9-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="c35c9-103">Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="c35c9-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="c35c9-104">Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo.</span><span class="sxs-lookup"><span data-stu-id="c35c9-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="c35c9-105">Nelle procedure riportate di seguito viene illustrato come creare un nuovo oggetto <xref:System.Windows.Forms.BindingSource> associato a un tipo, quindi come associare una delle proprietà del tipo alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di un oggetto <xref:System.Windows.Forms.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="c35c9-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="c35c9-106">Per associare BindingSource a un tipo</span><span class="sxs-lookup"><span data-stu-id="c35c9-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="c35c9-107">Creare un progetto di Windows Forms (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).</span><span class="sxs-lookup"><span data-stu-id="c35c9-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="c35c9-108">In visualizzazione **progettazione** trascinare un <xref:System.Windows.Forms.BindingSource> componente nel form.</span><span class="sxs-lookup"><span data-stu-id="c35c9-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="c35c9-109">Nella finestra **Proprietà** fare clic sulla freccia per la <xref:System.Windows.Forms.BindingSource.DataSource%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c35c9-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="c35c9-110">Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.</span><span class="sxs-lookup"><span data-stu-id="c35c9-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="c35c9-111">Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c35c9-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="c35c9-112">Selezionare il tipo da associare:</span><span class="sxs-lookup"><span data-stu-id="c35c9-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="c35c9-113">Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="c35c9-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="c35c9-114">\-oppure-</span><span class="sxs-lookup"><span data-stu-id="c35c9-114">\-or-</span></span>

    - <span data-ttu-id="c35c9-115">Se il tipo a cui si desidera eseguire l'associazione si trova in un altro assembly, non attualmente nell'elenco dei riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **progetti** . Selezionare il progetto che contiene l'oggetto business desiderato, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c35c9-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="c35c9-116">Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="c35c9-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="c35c9-117">Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.</span><span class="sxs-lookup"><span data-stu-id="c35c9-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="c35c9-118">Fare clic su **Avanti** e quindi su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c35c9-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="c35c9-119">Per associare il controllo a BindingSource</span><span class="sxs-lookup"><span data-stu-id="c35c9-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="c35c9-120">Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="c35c9-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="c35c9-121">Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="c35c9-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="c35c9-122">Fare clic sulla freccia accanto alla <xref:System.Windows.Forms.TextBox.Text%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c35c9-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="c35c9-123">Nell' **editor di tipo dell'interfaccia utente DataSource** espandere il nodo per l'oggetto <xref:System.Windows.Forms.BindingSource> aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di <xref:System.Windows.Forms.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="c35c9-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c35c9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c35c9-124">See also</span></span>

- [<span data-ttu-id="c35c9-125">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="c35c9-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="c35c9-126">Procedura: Associare un controllo di Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="c35c9-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="c35c9-127">Associare controlli ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c35c9-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
