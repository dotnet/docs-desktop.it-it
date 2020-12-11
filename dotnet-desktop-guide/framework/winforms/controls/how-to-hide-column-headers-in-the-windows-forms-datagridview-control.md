---
title: Nascondi intestazioni di colonna nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: d84c93b0ad1c9ef456c73dd29af1de4857778999
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964351"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>Procedura: Nascondere le intestazioni delle colonne nel controllo DataGridView di Windows Forms
In alcuni casi è necessario visualizzare <xref:System.Windows.Forms.DataGridView> senza intestazioni di colonna. Nel <xref:System.Windows.Forms.DataGridView> controllo, il <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> valore della proprietà determina se vengono visualizzate le intestazioni di colonna.  
  
### <a name="to-hide-the-column-headers"></a>Per nascondere le intestazioni di colonna  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> su `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
