---
title: Eseguire un'azione personalizzata in base alle modifiche apportate alla cella del controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963589"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="b2dee-102">Procedura: Eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2dee-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b2dee-103">Il <xref:System.Windows.Forms.DataGridView> controllo ha una serie di eventi che è possibile usare per rilevare le modifiche nello stato <xref:System.Windows.Forms.DataGridView> delle celle.</span><span class="sxs-lookup"><span data-stu-id="b2dee-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="b2dee-104">Due dei più comunemente usati sono gli <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventi e <xref:System.Windows.Forms.DataGridView.CellStateChanged> .</span><span class="sxs-lookup"><span data-stu-id="b2dee-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="b2dee-105">Per rilevare le modifiche apportate ai valori delle celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="b2dee-105">To detect changes in the values of DataGridView cells</span></span>  
  
- <span data-ttu-id="b2dee-106">Scrivere un gestore per l' <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="b2dee-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="b2dee-107">Per rilevare le modifiche apportate agli Stati delle celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="b2dee-107">To detect changes in the states of DataGridView cells</span></span>  
  
- <span data-ttu-id="b2dee-108">Scrivere un gestore per l' <xref:System.Windows.Forms.DataGridView.CellStateChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="b2dee-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2dee-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b2dee-109">Compiling the Code</span></span>  
 <span data-ttu-id="b2dee-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2dee-110">This example requires:</span></span>  
  
- <span data-ttu-id="b2dee-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="b2dee-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="b2dee-112">Per C#, è necessario connettere i gestori eventi agli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b2dee-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
- <span data-ttu-id="b2dee-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2dee-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2dee-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [<span data-ttu-id="b2dee-115">Programmazione con celle, righe e colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2dee-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [<span data-ttu-id="b2dee-116">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2dee-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
