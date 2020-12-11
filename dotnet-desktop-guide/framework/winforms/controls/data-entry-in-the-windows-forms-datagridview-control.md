---
title: Immissione di dati nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: e95095624f45cc1507735083a87293730e9133e9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951091"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="dd02a-102">Immissione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd02a-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dd02a-103">Il `DataGridView` controllo offre diverse funzionalità che consentono di modificare il modo in cui gli utenti aggiungono o modificano i dati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="dd02a-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="dd02a-104">Ad esempio, è possibile rendere più efficiente l'immissione dei dati fornendo i valori predefiniti per le nuove righe e avvisando gli utenti quando si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="dd02a-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd02a-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dd02a-105">In This Section</span></span>  
 [<span data-ttu-id="dd02a-106">Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd02a-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd02a-107">Viene descritto come modificare il modo in cui gli utenti iniziano a modificare le celle.</span><span class="sxs-lookup"><span data-stu-id="dd02a-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="dd02a-108">Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd02a-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="dd02a-109">Viene descritto come prepopolare la riga per i nuovi record per salvare l'ora di immissione dei dati.</span><span class="sxs-lookup"><span data-stu-id="dd02a-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="dd02a-110">Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd02a-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd02a-111">Descrive in modo dettagliato la riga per i nuovi record, incluse le informazioni su come nasconderla, sulla personalizzazione dell'aspetto e sulla correlazione alla <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="dd02a-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="dd02a-112">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd02a-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd02a-113">Viene descritto come convalidare l'input dell'utente per impedire errori di formattazione di voci di dati.</span><span class="sxs-lookup"><span data-stu-id="dd02a-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="dd02a-114">Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd02a-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="dd02a-115">Viene descritto come gestire gli errori di immissione dati originati dall'origine dati quando l'utente tenta di eseguire il commit di un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="dd02a-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dd02a-116">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="dd02a-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="dd02a-117">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="dd02a-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="dd02a-118">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridView.EditMode%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="dd02a-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="dd02a-119">Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.</span><span class="sxs-lookup"><span data-stu-id="dd02a-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="dd02a-120">Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridView.DataError> evento.</span><span class="sxs-lookup"><span data-stu-id="dd02a-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="dd02a-121">Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridView.CellValidating> evento.</span><span class="sxs-lookup"><span data-stu-id="dd02a-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dd02a-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="dd02a-122">Related Sections</span></span>  
 [<span data-ttu-id="dd02a-123">Visualizzazione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd02a-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd02a-124">Fornisce argomenti che descrivono come popolare il controllo con i dati manualmente o da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="dd02a-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd02a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd02a-125">See also</span></span>

- [<span data-ttu-id="dd02a-126">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="dd02a-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="dd02a-127">Tipi di colonna nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd02a-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
