---
title: "Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: d65dd038ddc276ec09a1db3af4f14fc87fec56f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962851"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7a41-102">Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7a41-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="d7a41-103">La gestione degli errori dall'archivio dati sottostante è una funzionalità obbligatoria per un'applicazione di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="d7a41-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="d7a41-104">Il <xref:System.Windows.Forms.DataGridView> controllo Windows Forms semplifica questa operazione esponendo l' <xref:System.Windows.Forms.DataGridView.DataError> evento, che viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business interruppe.</span><span class="sxs-lookup"><span data-stu-id="d7a41-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="d7a41-105">In questa procedura dettagliata vengono recuperate le righe dalla `Customers` tabella nel database di esempio Northwind e visualizzate in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="d7a41-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7a41-106">Quando `CustomerID` viene rilevato un valore duplicato in una nuova riga o in una riga esistente modificata, l' <xref:System.Windows.Forms.DataGridView.DataError> evento si verificherà, che verrà gestito visualizzando un oggetto <xref:System.Windows.Forms.MessageBox> che descrive l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d7a41-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="d7a41-107">Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7a41-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d7a41-108">Prerequisites</span></span>

<span data-ttu-id="d7a41-109">Per completare questo scenario, saranno necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7a41-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="d7a41-110">Accesso a un server in cui è presente il database di esempio Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7a41-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="d7a41-111">Creazione del form</span><span class="sxs-lookup"><span data-stu-id="d7a41-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="d7a41-112">Per gestire gli errori di immissione dei dati nel controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="d7a41-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="d7a41-113">Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="d7a41-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="d7a41-114">Nell'esempio di codice seguente viene fornita l'inizializzazione di base e viene incluso un `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="d7a41-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="d7a41-115">Implementare un metodo nella definizione di classe del modulo per la gestione dei dettagli della connessione al database.</span><span class="sxs-lookup"><span data-stu-id="d7a41-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="d7a41-116">Questo esempio di codice usa un `GetData` metodo che restituisce un <xref:System.Data.DataTable> oggetto popolato.</span><span class="sxs-lookup"><span data-stu-id="d7a41-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="d7a41-117">Assicurarsi di impostare la `connectionString` variabile su un valore appropriato per il database.</span><span class="sxs-lookup"><span data-stu-id="d7a41-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d7a41-118">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7a41-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d7a41-119">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="d7a41-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d7a41-120">Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).</span><span class="sxs-lookup"><span data-stu-id="d7a41-120">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="d7a41-121">Implementare un gestore per l'evento del form <xref:System.Windows.Forms.Form.Load> che inizializza <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> imposta il data binding.</span><span class="sxs-lookup"><span data-stu-id="d7a41-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="d7a41-122">Gestire l' <xref:System.Windows.Forms.DataGridView.DataError> evento su <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="d7a41-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="d7a41-123">Se il contesto per l'errore è un'operazione di commit, visualizzare l'errore in un oggetto <xref:System.Windows.Forms.MessageBox> .</span><span class="sxs-lookup"><span data-stu-id="d7a41-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="d7a41-124">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d7a41-124">Testing the Application</span></span>

<span data-ttu-id="d7a41-125">È ora possibile testare il form per assicurarsi che si comportano come previsto.</span><span class="sxs-lookup"><span data-stu-id="d7a41-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="d7a41-126">Per testare il modulo</span><span class="sxs-lookup"><span data-stu-id="d7a41-126">To test the form</span></span>

- <span data-ttu-id="d7a41-127">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7a41-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="d7a41-128">Viene visualizzato un <xref:System.Windows.Forms.DataGridView> controllo compilato con i dati della tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="d7a41-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="d7a41-129">Se si immette un valore duplicato per `CustomerID` e si esegue il commit della modifica, il valore della cella verrà ripristinato automaticamente e verrà <xref:System.Windows.Forms.MessageBox> visualizzato un messaggio in cui viene visualizzato l'errore di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="d7a41-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7a41-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d7a41-130">Next Steps</span></span>

<span data-ttu-id="d7a41-131">Questa applicazione offre una conoscenza di base delle <xref:System.Windows.Forms.DataGridView> funzionalità del controllo.</span><span class="sxs-lookup"><span data-stu-id="d7a41-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="d7a41-132">È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="d7a41-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="d7a41-133">Modificare gli stili del bordo e dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="d7a41-133">Change border and header styles.</span></span> <span data-ttu-id="d7a41-134">Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="d7a41-135">Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="d7a41-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7a41-136">Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: creare colonne Read-Only nel controllo Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="d7a41-137">Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="d7a41-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7a41-138">Per ulteriori informazioni, vedere [procedura dettagliata: convalida dei dati nel controllo DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="d7a41-139">Gestire set di dati di grandi dimensioni usando la modalità virtuale.</span><span class="sxs-lookup"><span data-stu-id="d7a41-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="d7a41-140">Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="d7a41-141">Personalizzare l'aspetto delle celle.</span><span class="sxs-lookup"><span data-stu-id="d7a41-141">Customize the appearance of cells.</span></span> <span data-ttu-id="d7a41-142">Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d7a41-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7a41-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7a41-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d7a41-144">Immissione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7a41-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7a41-145">Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7a41-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="d7a41-146">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7a41-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7a41-147">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="d7a41-147">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
