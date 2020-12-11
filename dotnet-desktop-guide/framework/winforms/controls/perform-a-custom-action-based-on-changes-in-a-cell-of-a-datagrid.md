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
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Procedura: Eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Forms
Il <xref:System.Windows.Forms.DataGridView> controllo ha una serie di eventi che è possibile usare per rilevare le modifiche nello stato <xref:System.Windows.Forms.DataGridView> delle celle. Due dei più comunemente usati sono gli <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventi e <xref:System.Windows.Forms.DataGridView.CellStateChanged> .  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Per rilevare le modifiche apportate ai valori delle celle DataGridView  
  
- Scrivere un gestore per l' <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Per rilevare le modifiche apportate agli Stati delle celle DataGridView  
  
- Scrivere un gestore per l' <xref:System.Windows.Forms.DataGridView.CellStateChanged> evento.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`. Per C#, è necessario connettere i gestori eventi agli eventi corrispondenti.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Programmazione con celle, righe e colonne nel controllo DataGridView di Windows Form](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
