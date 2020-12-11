---
title: Ordinamento di dati nel controllo DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966097"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="140a4-102">Ordinamento dei dati nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="140a4-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="140a4-103">Per impostazione predefinita, gli utenti possono ordinare i dati in un <xref:System.Windows.Forms.DataGridView> controllo facendo clic sull'intestazione di una colonna della casella di testo (o premendo F3 quando una cella della casella di testo è concentrata su .NET Framework 4.7.2 e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="140a4-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="140a4-104">È possibile modificare la <xref:System.Windows.Forms.DataGridViewColumn.SortMode> proprietà di colonne specifiche per consentire agli utenti di eseguire l'ordinamento in base ad altri tipi di colonna quando è opportuno eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="140a4-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="140a4-105">È anche possibile ordinare i dati a livello di codice in base a qualsiasi colonna o a più colonne.</span><span class="sxs-lookup"><span data-stu-id="140a4-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="140a4-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="140a4-106">In this section</span></span>

[<span data-ttu-id="140a4-107">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="140a4-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="140a4-108">Descrive le opzioni per l'ordinamento dei dati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="140a4-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="140a4-109">Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="140a4-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="140a4-110">Viene descritto come consentire agli utenti di eseguire l'ordinamento in base a colonne non ordinabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="140a4-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="140a4-111">Procedura: personalizzare l'ordinamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="140a4-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="140a4-112">Viene descritto come ordinare i dati a livello di codice e come personalizzare l'ordinamento utilizzando l' <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> evento o implementando l' <xref:System.Collections.IComparer> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="140a4-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="140a4-113">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="140a4-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="140a4-114">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="140a4-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="140a4-115">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="140a4-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="140a4-116">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="140a4-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="140a4-117">Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="140a4-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="140a4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="140a4-118">See also</span></span>

- [<span data-ttu-id="140a4-119">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="140a4-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="140a4-120">Tipi di colonna nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="140a4-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
