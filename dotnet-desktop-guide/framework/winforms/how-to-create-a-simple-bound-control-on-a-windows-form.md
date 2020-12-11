---
title: 'Procedura: Creare un controllo con associazione semplice in un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: bb7554831ab3698333850b71c42a5343ceb7d682
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951358"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="1395e-102">Procedura: creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="1395e-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="1395e-103">Con l' *associazione semplice*, è possibile visualizzare un singolo elemento dati, ad esempio un valore di colonna da una tabella del set di dati, in un controllo.</span><span class="sxs-lookup"><span data-stu-id="1395e-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="1395e-104">È possibile associare in modo semplice qualsiasi proprietà di un controllo a un valore di dati.</span><span class="sxs-lookup"><span data-stu-id="1395e-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="1395e-105">Per eseguire l'associazione semplice di un controllo</span><span class="sxs-lookup"><span data-stu-id="1395e-105">To simple-bind a control</span></span>

1. <span data-ttu-id="1395e-106">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1395e-106">Connect to a data source.</span></span> <span data-ttu-id="1395e-107">Per ulteriori informazioni, vedere [connessione a un'origine dati](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span><span class="sxs-lookup"><span data-stu-id="1395e-107">For more information, see [Connecting to a Data Source](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span></span>

2. <span data-ttu-id="1395e-108">In Visual Studio selezionare il controllo nel form e visualizzare la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="1395e-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="1395e-109">Espandere la proprietà **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="1395e-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="1395e-110">Le proprietà associate più spesso vengono visualizzate sotto la proprietà **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="1395e-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="1395e-111">Nella maggior parte dei controlli, ad esempio, la proprietà **Text** viene associata con maggiore frequenza.</span><span class="sxs-lookup"><span data-stu-id="1395e-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="1395e-112">Se la proprietà che si desidera associare non è una delle proprietà comunemente associate, fare **clic sul pulsante con i puntini** di sospensione ( ![ ...) nella finestra proprietà di Visual Studio. ](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png) ) nella casella **(avanzate)** per visualizzare la finestra di dialogo **formattazione e associazione avanzata** con un elenco completo delle proprietà per il controllo.</span><span class="sxs-lookup"><span data-stu-id="1395e-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="1395e-113">Selezionare la proprietà che si desidera associare, quindi fare clic sulla freccia a discesa sotto **Binding**.</span><span class="sxs-lookup"><span data-stu-id="1395e-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="1395e-114">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="1395e-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="1395e-115">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="1395e-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="1395e-116">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="1395e-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="1395e-117">Fare clic sul nome dell'elemento a cui effettuare il binding.</span><span class="sxs-lookup"><span data-stu-id="1395e-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="1395e-118">Se si utilizza la finestra di dialogo **formattazione e binding avanzato** , fare clic su **OK** per tornare alla finestra **proprietà** .</span><span class="sxs-lookup"><span data-stu-id="1395e-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="1395e-119">Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.</span><span class="sxs-lookup"><span data-stu-id="1395e-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1395e-120">Poiché i controlli con associazione semplice mostrano solo un singolo elemento dati, è molto normale includere la logica di navigazione in un Windows Form con controlli ad associazione semplice.</span><span class="sxs-lookup"><span data-stu-id="1395e-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="1395e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1395e-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="1395e-122">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1395e-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="1395e-123">Associazione dati e Windows Form</span><span class="sxs-lookup"><span data-stu-id="1395e-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
