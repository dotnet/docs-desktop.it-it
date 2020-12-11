---
title: Aggiungere descrizioni comandi a singole celle nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952656"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Procedura: Aggiungere descrizioni comando alle singole celle in un controllo DataGridView di Windows Forms
Per impostazione predefinita, le descrizioni comandi vengono utilizzate per visualizzare i valori delle <xref:System.Windows.Forms.DataGridView> celle troppo piccole per visualizzare l'intero contenuto. È tuttavia possibile eseguire l'override di questo comportamento per impostare i valori di testo della descrizione comando per le singole celle. Questa operazione è utile per visualizzare agli utenti informazioni aggiuntive su una cella o per fornire agli utenti una descrizione alternativa del contenuto della cella. Se, ad esempio, è presente una riga in cui sono visualizzate le icone di stato, è possibile fornire spiegazioni del testo utilizzando le descrizioni comandi.  
  
 È anche possibile disabilitare la visualizzazione delle descrizioni comando a livello di cella impostando la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> proprietà su `false` .  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Per aggiungere una descrizione comando a una cella  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- L'esempio presenta i requisiti seguenti:  
  
- Un <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `Rating` per la visualizzazione dei valori stringa di uno e quattro simboli asterisco ("*"). L' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento del controllo deve essere associato al metodo del gestore eventi illustrato nell'esempio.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Quando si associa il <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati esterna o si fornisce un'origine dati personalizzata implementando la modalità virtuale, è possibile che si verifichino problemi di prestazioni. Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, gestire l' <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> evento anziché impostare la <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà di più celle. Quando si gestisce questo evento, ottenere il valore di una proprietà della cella <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> genera l'evento e restituisce il valore della <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> proprietà come specificato nel gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Programmazione con celle, righe e colonne nel controllo DataGridView di Windows Form](programming-with-cells-rows-and-columns-in-the-datagrid.md)
