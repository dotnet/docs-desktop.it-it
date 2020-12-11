---
title: Impostare la modalità di selezione del controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: da866aac3ac5b08a06ec71744aadb4260bd0cfc4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965215"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="538c8-102">Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="538c8-102">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="538c8-103">Nell'esempio di codice seguente viene illustrato come configurare un <xref:System.Windows.Forms.DataGridView> controllo in modo che facendo clic in un punto qualsiasi all'interno di una riga venga selezionata automaticamente l'intera riga, in modo che sia possibile selezionare solo una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="538c8-103">The following code example demonstrates how to configure a <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row automatically selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="538c8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="538c8-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="538c8-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="538c8-105">Compiling the Code</span></span>  
 <span data-ttu-id="538c8-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="538c8-106">This example requires:</span></span>  
  
- <span data-ttu-id="538c8-107">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="538c8-107">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="538c8-108">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="538c8-108">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538c8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="538c8-109">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [<span data-ttu-id="538c8-110">Utilizzo della selezione e degli Appunti con il controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="538c8-110">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="538c8-111">Modalità di selezione nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="538c8-111">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
