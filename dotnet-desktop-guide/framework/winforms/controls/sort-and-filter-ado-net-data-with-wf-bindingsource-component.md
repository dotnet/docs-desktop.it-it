---
title: Ordinare e filtrare i dati di ADO.NET con il componente BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 404e67f1eeed240a171cb1cfef9094a746c3cecb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951394"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="72f7b-102">Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72f7b-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>

<span data-ttu-id="72f7b-103">È possibile esporre le funzionalità di ordinamento e filtro del <xref:System.Windows.Forms.BindingSource> controllo tramite le <xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà e.</span><span class="sxs-lookup"><span data-stu-id="72f7b-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="72f7b-104">È possibile applicare l'ordinamento semplice quando l'origine dati sottostante è un oggetto <xref:System.ComponentModel.IBindingList> ed è possibile applicare il filtro e l'ordinamento avanzato quando l'origine dati è un oggetto <xref:System.ComponentModel.IBindingListView> .</span><span class="sxs-lookup"><span data-stu-id="72f7b-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="72f7b-105">La <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà richiede la sintassi ADO.NET standard: una stringa che rappresenta il nome di una colonna di dati nell'origine dati seguita da `ASC` o `DESC` per indicare se l'elenco deve essere ordinato in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="72f7b-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="72f7b-106">È possibile impostare l'ordinamento avanzato o l'ordinamento a più colonne separando ogni colonna con un separatore virgola.</span><span class="sxs-lookup"><span data-stu-id="72f7b-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="72f7b-107">La <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà accetta un'espressione stringa.</span><span class="sxs-lookup"><span data-stu-id="72f7b-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72f7b-108">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72f7b-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="72f7b-109">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="72f7b-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="72f7b-110">Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).</span><span class="sxs-lookup"><span data-stu-id="72f7b-110">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="72f7b-111">Per filtrare i dati con BindingSource</span><span class="sxs-lookup"><span data-stu-id="72f7b-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="72f7b-112">Impostare la <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà su espressione desiderata.</span><span class="sxs-lookup"><span data-stu-id="72f7b-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="72f7b-113">Nell'esempio di codice seguente, l'espressione è un nome di colonna seguito da un valore che si desidera per la colonna.</span><span class="sxs-lookup"><span data-stu-id="72f7b-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="72f7b-114">Per ordinare i dati con BindingSource</span><span class="sxs-lookup"><span data-stu-id="72f7b-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="72f7b-115">Impostare la <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà sul nome della colonna che si desidera seguito da `ASC` o `DESC` per indicare l'ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="72f7b-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="72f7b-116">Separare più colonne con una virgola.</span><span class="sxs-lookup"><span data-stu-id="72f7b-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="72f7b-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="72f7b-117">Example</span></span>  

 <span data-ttu-id="72f7b-118">L'esempio di codice seguente consente di caricare i dati dalla tabella Customers del database di esempio Northwind in un <xref:System.Windows.Forms.DataGridView> controllo e di filtrare e ordinare i dati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="72f7b-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72f7b-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="72f7b-119">Compiling the Code</span></span>  

 <span data-ttu-id="72f7b-120">Per eseguire questo esempio, incollare il codice in un form che contiene un oggetto <xref:System.Windows.Forms.BindingSource> denominato `BindingSource1` e un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` .</span><span class="sxs-lookup"><span data-stu-id="72f7b-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="72f7b-121">Gestire l' <xref:System.Windows.Forms.Form.Load> evento per il form e chiamare `InitializeSortedFilteredBindingSource` nel metodo del gestore dell'evento Load.</span><span class="sxs-lookup"><span data-stu-id="72f7b-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f7b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f7b-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="72f7b-123">[Procedura: Installare database di esempio](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="72f7b-123">[How to: Install Sample Databases](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="72f7b-124">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="72f7b-124">BindingSource Component</span></span>](bindingsource-component.md)
