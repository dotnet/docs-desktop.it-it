---
title: Specificare la modalità di modifica per il controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964855"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Forms
Per impostazione predefinita, gli utenti possono modificare il contenuto della <xref:System.Windows.Forms.DataGridView> cella della casella di testo corrente digitando o premendo F2. In questo modo, la cella viene attivata in modalità di modifica se vengono soddisfatte tutte le condizioni seguenti:  
  
- L'origine dati sottostante supporta la modifica.  
  
- Il <xref:System.Windows.Forms.DataGridView> controllo è abilitato.  
  
- Il valore della proprietà <xref:System.Windows.Forms.DataGridView.EditMode%2A> non è <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- Le `ReadOnly` proprietà della cella, della riga, della colonna e del controllo sono tutte impostate su `false` .  
  
 In modalità di modifica, l'utente può modificare il valore della cella e premere INVIO per eseguire il commit della modifica o dell'ESC per ripristinare il valore originale della cella.  
  
 È possibile configurare un <xref:System.Windows.Forms.DataGridView> controllo in modo che una cella entri in modalità di modifica non appena diventa la cella corrente. In questo caso, il comportamento dei tasti ENTER e ESC è invariato, ma la cella rimane in modalità di modifica dopo il commit o il ripristino del valore. È anche possibile configurare il controllo in modo che le celle entrino in modalità di modifica solo quando gli utenti digitano la cella o solo quando gli utenti preme F2. Infine, è possibile impedire che le celle entrino in modalità di modifica tranne quando si chiama il <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> metodo.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Per modificare la modalità di modifica di un controllo DataGridView  
  
- Impostare la <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> proprietà sull'enumerazione appropriata <xref:System.Windows.Forms.DataGridViewEditMode> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System> e <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
