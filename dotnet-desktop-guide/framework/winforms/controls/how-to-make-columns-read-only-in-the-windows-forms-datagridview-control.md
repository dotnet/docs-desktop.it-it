---
title: Read-Only di colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952121"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>Procedura: Impostare le colonne come di sola lettura nel controllo DataGridView di Windows Forms
Non tutti i dati sono concepiti per la modifica. Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> di una colonna determina se gli utenti possono modificare le celle di tale colonna. Per informazioni su come rendere il controllo interamente di sola lettura, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md).  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [procedura: creare colonne Read-Only nel controllo DataGridView Windows Forms mediante la finestra di progettazione](make-columns-read-only-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-make-a-column-read-only-programmatically"></a>Per impostare una colonna come di sola lettura a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> su `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna denominata `CompanyName`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms](prevent-row-addition-and-deletion-datagridview.md)
