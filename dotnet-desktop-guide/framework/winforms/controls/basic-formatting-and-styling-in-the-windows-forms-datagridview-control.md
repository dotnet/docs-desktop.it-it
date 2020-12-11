---
title: Formattazione e stile di base nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952643"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="94878-102">Formattazione e stile di base nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="94878-103">Il `DataGridView` controllo consente di definire in modo semplice l'aspetto di base delle celle e la formattazione di visualizzazione dei valori delle celle.</span><span class="sxs-lookup"><span data-stu-id="94878-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="94878-104">È possibile definire gli stili di aspetto e formattazione per le singole celle, per le celle in colonne e righe specifiche o per tutte le celle nel controllo impostando le proprietà degli oggetti a cui si `DataGridViewCellStyle` accede tramite varie `DataGridView` proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="94878-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="94878-105">Inoltre, è possibile modificare questi stili in modo dinamico in base a fattori come il valore della cella gestendo l' `CellFormatting` evento.</span><span class="sxs-lookup"><span data-stu-id="94878-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94878-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="94878-106">In This Section</span></span>  
 [<span data-ttu-id="94878-107">Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94878-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="94878-108">Viene descritto come impostare le `DataGridView` proprietà che definiscono l'aspetto del bordo del controllo e le linee limite tra le celle.</span><span class="sxs-lookup"><span data-stu-id="94878-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="94878-109">Stili della cella nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-110">Descrive la `DataGridViewCellStyle` classe e il modo in cui le proprietà di quel tipo interagiscono per definire come vengono visualizzate le celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="94878-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="94878-111">Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94878-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-112">Viene descritto come utilizzare le `DataGridViewCellStyle` proprietà per definire l'aspetto predefinito delle celle in righe e colonne specifiche e nell'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="94878-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="94878-113">Procedura: Formattare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-114">Viene descritto come formattare i valori di visualizzazione delle celle usando le `DataGridViewCellStyle` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="94878-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="94878-115">Procedura: Impostare gli stili di carattere e colore nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-116">Viene descritto come utilizzare la `DefaultCellStyle` proprietà per impostare le caratteristiche di visualizzazione di base per tutte le celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="94878-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="94878-117">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94878-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-118">Viene descritto come creare un effetto di tipo Ledger nel controllo utilizzando righe alternate visualizzate in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="94878-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="94878-119">Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94878-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="94878-120">Viene descritto come utilizzare la `RowTemplate` proprietà per impostare le proprietà delle righe che verranno utilizzate per tutte le righe nel controllo.</span><span class="sxs-lookup"><span data-stu-id="94878-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="94878-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="94878-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="94878-122">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="94878-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="94878-123">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewCellStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="94878-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="94878-124">Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.</span><span class="sxs-lookup"><span data-stu-id="94878-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="94878-125">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="94878-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94878-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="94878-126">Related Sections</span></span>  
 [<span data-ttu-id="94878-127">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="94878-128">Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.</span><span class="sxs-lookup"><span data-stu-id="94878-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="94878-129">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="94878-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="94878-130">Fornisce argomenti che descrivono le proprietà di celle, righe e colonne comunemente utilizzate.</span><span class="sxs-lookup"><span data-stu-id="94878-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94878-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94878-131">See also</span></span>

- [<span data-ttu-id="94878-132">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="94878-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
