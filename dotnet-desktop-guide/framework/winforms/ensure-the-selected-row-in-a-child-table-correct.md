---
title: 'Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: 1047958a5600d8e6ee0ba461305e09395151ab14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963478"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="754ef-102">Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta</span><span class="sxs-lookup"><span data-stu-id="754ef-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="754ef-103">Quando si usa il data binding in Windows Form, spesso i dati vengono mostrati in una visualizzazione denominata padre/figlio o master/dettagli</span><span class="sxs-lookup"><span data-stu-id="754ef-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="754ef-104">Si tratta di uno scenario di data binding in cui i dati provenienti dalla stessa origine vengono visualizzati in due controlli.</span><span class="sxs-lookup"><span data-stu-id="754ef-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="754ef-105">Se si modifica la selezione in un controllo, automaticamente vengono modificati anche i dati visualizzati nel secondo controllo.</span><span class="sxs-lookup"><span data-stu-id="754ef-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="754ef-106">Ad esempio, il primo controllo può contenere un elenco di clienti e il secondo un elenco di ordini correlati al cliente selezionato nel primo controllo.</span><span class="sxs-lookup"><span data-stu-id="754ef-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="754ef-107">A partire da .NET Framework versione 2.0, quando si visualizzano i dati in una visualizzazione padre/figlio può essere necessario effettuare alcuni passaggi aggiuntivi per assicurarsi che la riga attualmente selezionata nella tabella figlio non venga reimpostata sulla prima riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="754ef-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="754ef-108">A tale scopo, è necessario memorizzare nella cache la posizione della tabella figlio e reimpostarla dopo aver modificato la tabella padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="754ef-109">In genere, la tabella figlio viene reimpostata la prima volta che si modifica un campo in una riga della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="754ef-110">Per memorizzare nella cache la posizione corrente della tabella figlio</span><span class="sxs-lookup"><span data-stu-id="754ef-110">To Cache the Current Child Position</span></span>  
  
1. <span data-ttu-id="754ef-111">Dichiarare una variabile Integer per archiviare la posizione dell'elenco figlio e una variabile booleana per archiviare se memorizzare nella cache la posizione della tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="754ef-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2. <span data-ttu-id="754ef-112">Gestire l'evento <xref:System.Windows.Forms.CurrencyManager.ListChanged> per l'oggetto <xref:System.Windows.Forms.CurrencyManager> dell'associazione e individuare un oggetto <xref:System.ComponentModel.ListChangedType> di <xref:System.ComponentModel.ListChangedType.Reset>.</span><span class="sxs-lookup"><span data-stu-id="754ef-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3. <span data-ttu-id="754ef-113">Controllare la posizione corrente dell'oggetto <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="754ef-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="754ef-114">Se è maggiore del primo elemento dell'elenco, in genere 0, salvarlo in una variabile.</span><span class="sxs-lookup"><span data-stu-id="754ef-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="754ef-115">Gestire l'evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> dell'elenco padre per l'oggetto CurrencyManager padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="754ef-116">Nel gestore impostare il valore booleano per indicare che non si tratta di uno scenario di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="754ef-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="754ef-117">Se si verifica l'evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, la modifica all'elemento padre sarà una modifica alla posizione dell'elenco e non una modifica al valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="754ef-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="754ef-118">Per reimpostare la posizione dell'elemento figlio</span><span class="sxs-lookup"><span data-stu-id="754ef-118">To Reset the Child Position</span></span>  
  
1. <span data-ttu-id="754ef-119">Gestire l'evento <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> per l'oggetto <xref:System.Windows.Forms.CurrencyManager> del binding figlio.</span><span class="sxs-lookup"><span data-stu-id="754ef-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2. <span data-ttu-id="754ef-120">Reimpostare la posizione della tabella figlio sulla posizione memorizzata nella cache salvata nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="754ef-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="754ef-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="754ef-121">Example</span></span>  
 <span data-ttu-id="754ef-122">L'esempio seguente illustra come salvare la posizione corrente nell'oggetto <xref:System.Windows.Forms.CurrencyManager> per una tabella figlio e reimpostare la posizione dopo aver effettuato una modifica nella tabella padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="754ef-123">In questo esempio sono presenti due controlli <xref:System.Windows.Forms.DataGridView> associati a due tabelle in un oggetto <xref:System.Data.DataSet> mediante un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="754ef-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="754ef-124">Tra le due tabelle viene stabilita una relazione, che viene aggiunta all'oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="754ef-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="754ef-125">La posizione nella tabella figlio viene impostata inizialmente sulla terza riga a mero scopo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="754ef-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="754ef-126">Per testare l'esempio di codice, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="754ef-126">To test the code example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="754ef-127">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="754ef-127">Run the example.</span></span>  
  
2. <span data-ttu-id="754ef-128">Verificare che la casella di controllo **Memorizza nella cache e reimposta posizione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="754ef-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3. <span data-ttu-id="754ef-129">Fare clic sul pulsante **Cancella campo padre** per provocare una modifica in un campo della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="754ef-130">Notare che la riga selezionata nella tabella figlio non cambia.</span><span class="sxs-lookup"><span data-stu-id="754ef-130">Notice that the selected row in the child table does not change.</span></span>  
  
4. <span data-ttu-id="754ef-131">Chiudere ed eseguire nuovamente l'esempio.</span><span class="sxs-lookup"><span data-stu-id="754ef-131">Close and run the example again.</span></span> <span data-ttu-id="754ef-132">È necessario eseguire questa procedura perché la reimpostazione si verifica solo in seguito alla prima modifica nella riga padre.</span><span class="sxs-lookup"><span data-stu-id="754ef-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5. <span data-ttu-id="754ef-133">Deselezionare la casella di controllo **Memorizza nella cache e reimposta posizione**.</span><span class="sxs-lookup"><span data-stu-id="754ef-133">Clear the **Cache and reset position** check box.</span></span>  
  
6. <span data-ttu-id="754ef-134">Fare clic sul pulsante **Cancella campo padre**.</span><span class="sxs-lookup"><span data-stu-id="754ef-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="754ef-135">Notare che la riga selezionata nella tabella figlio diventa la prima riga.</span><span class="sxs-lookup"><span data-stu-id="754ef-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="754ef-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="754ef-136">Compiling the Code</span></span>  
 <span data-ttu-id="754ef-137">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="754ef-137">This example requires:</span></span>  
  
- <span data-ttu-id="754ef-138">Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="754ef-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754ef-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="754ef-139">See also</span></span>

- [<span data-ttu-id="754ef-140">Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati</span><span class="sxs-lookup"><span data-stu-id="754ef-140">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)
- [<span data-ttu-id="754ef-141">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="754ef-141">BindingSource Component</span></span>](./controls/bindingsource-component.md)
- [<span data-ttu-id="754ef-142">Associazione dati e Windows Form</span><span class="sxs-lookup"><span data-stu-id="754ef-142">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
