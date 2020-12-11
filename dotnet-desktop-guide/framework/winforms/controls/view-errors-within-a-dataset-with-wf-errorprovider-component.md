---
title: Visualizzazione degli errori in un set di dati tramite il componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966682"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="55aee-102">Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55aee-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="55aee-103">È possibile utilizzare il <xref:System.Windows.Forms.ErrorProvider> componente Windows Forms per visualizzare gli errori di colonna all'interno di un set di dati o di un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="55aee-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="55aee-104">Per <xref:System.Windows.Forms.ErrorProvider> visualizzare gli errori relativi ai dati in un form, un componente non deve essere direttamente associato a un controllo.</span><span class="sxs-lookup"><span data-stu-id="55aee-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="55aee-105">Una volta associato a un'origine dati, è possibile che venga visualizzata un'icona di errore accanto a qualsiasi controllo associato alla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="55aee-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55aee-106">Se si modificano le proprietà e del provider di errori in fase di <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> esecuzione, è necessario utilizzare il <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> metodo per evitare conflitti.</span><span class="sxs-lookup"><span data-stu-id="55aee-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="55aee-107">Per visualizzare gli errori relativi ai dati</span><span class="sxs-lookup"><span data-stu-id="55aee-107">To display data errors</span></span>  
  
1. <span data-ttu-id="55aee-108">Associare il componente a una colonna specifica in una tabella di dati.</span><span class="sxs-lookup"><span data-stu-id="55aee-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2. <span data-ttu-id="55aee-109">Impostare la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà sul form.</span><span class="sxs-lookup"><span data-stu-id="55aee-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="55aee-110">Consente di impostare la posizione del record corrente su una riga contenente un errore di colonna.</span><span class="sxs-lookup"><span data-stu-id="55aee-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="55aee-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55aee-111">See also</span></span>

- [<span data-ttu-id="55aee-112">Panoramica del componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="55aee-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="55aee-113">Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55aee-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
