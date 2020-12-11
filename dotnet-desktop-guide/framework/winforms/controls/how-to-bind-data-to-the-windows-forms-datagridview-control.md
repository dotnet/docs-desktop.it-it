---
title: Associare dati al controllo DataGridView
ms.date: 02/08/2019
description: Informazioni sul modo in cui il controllo DataGridView supporta il modello di data binding Windows Forms standard in modo che possa essere associato a un'ampia gamma di origini dati.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 7daf68691ee67472ab8cfba7b396faeffa27a206
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963970"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="7f3d8-103">Procedura: associare dati al controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f3d8-103">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="7f3d8-104">Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di data binding Windows Forms standard, in modo che possa essere associato a un'ampia gamma di origini dati.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="7f3d8-105">In genere, si esegue l'associazione a un oggetto <xref:System.Windows.Forms.BindingSource> che gestisce l'interazione con l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-105">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="7f3d8-106"><xref:System.Windows.Forms.BindingSource>Può essere qualsiasi origine dati Windows Forms, che offre una grande flessibilità durante la scelta o la modifica del percorso dei dati.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-106">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="7f3d8-107">Per ulteriori informazioni sulle origini dati <xref:System.Windows.Forms.DataGridView> supportate dal controllo, vedere [Cenni preliminari sul controllo DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7f3d8-107">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="7f3d8-108">Visual Studio offre supporto esteso per data binding al controllo DataGridView.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-108">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="7f3d8-109">Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms usando la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="7f3d8-109">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="7f3d8-110">Per connettere un controllo DataGridView ai dati:</span><span class="sxs-lookup"><span data-stu-id="7f3d8-110">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="7f3d8-111">Implementare un metodo per gestire i dettagli del recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-111">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="7f3d8-112">Nell'esempio di codice seguente viene implementato un `GetData` metodo che Inizializza un oggetto <xref:System.Data.SqlClient.SqlDataAdapter> e lo utilizza per popolare un oggetto <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="7f3d8-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="7f3d8-113">Associa quindi <xref:System.Data.DataTable> a <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="7f3d8-113">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="7f3d8-114">Nel <xref:System.Windows.Forms.Form.Load> gestore eventi del form, associare il <xref:System.Windows.Forms.DataGridView> controllo a <xref:System.Windows.Forms.BindingSource> e chiamare il `GetData` metodo per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-114">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="7f3d8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f3d8-115">Example</span></span>

<span data-ttu-id="7f3d8-116">Questo esempio di codice completo recupera i dati da un database per popolare un controllo DataGridView in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-116">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="7f3d8-117">Il modulo include anche pulsanti per ricaricare i dati e inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-117">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="7f3d8-118">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f3d8-118">This example requires:</span></span>

- <span data-ttu-id="7f3d8-119">Accesso a un database di esempio Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-119">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="7f3d8-120">Per ulteriori informazioni sull'installazione del database di esempio Northwind, vedere [ottenere i database di esempio per esempi di codice ADO.NET](/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases).</span><span class="sxs-lookup"><span data-stu-id="7f3d8-120">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases).</span></span>

- <span data-ttu-id="7f3d8-121">Riferimenti agli assembly System, System. Windows. Forms, System. Data e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-121">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="7f3d8-122">Per compilare ed eseguire questo esempio, incollare il codice nel file di codice *Form1* in un nuovo progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-122">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="7f3d8-123">Per informazioni sulla compilazione dalla riga di comando C# o Visual Basic, vedere compilazione dalla [riga di comando con csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) o [compilazione dalla riga di comando](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="7f3d8-123">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Build from the command line](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>  
  
<span data-ttu-id="7f3d8-124">Popolare la `connectionString` variabile nell'esempio con i valori per la connessione al database di esempio Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-124">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="7f3d8-125">L'autenticazione di Windows, detta anche sicurezza integrata, è un modo più sicuro per connettersi al database rispetto all'archiviazione di una password nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="7f3d8-125">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="7f3d8-126">Per ulteriori informazioni sulla sicurezza della connessione, vedere [proteggere le informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).</span><span class="sxs-lookup"><span data-stu-id="7f3d8-126">For more information about connection security, see [Protect connection information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7f3d8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f3d8-127">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="7f3d8-128">Visualizzare i dati nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f3d8-128">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7f3d8-129">Proteggere le informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="7f3d8-129">Protect connection information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
