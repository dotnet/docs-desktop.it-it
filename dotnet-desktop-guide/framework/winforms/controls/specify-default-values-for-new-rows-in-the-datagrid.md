---
title: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964291"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Forms
È possibile rendere più semplice l'immissione dei dati quando l'applicazione compila i valori predefiniti per le nuove righe aggiunte. Con la <xref:System.Windows.Forms.DataGridView> classe, è possibile inserire i valori predefiniti con l' <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento. Questo evento viene generato quando l'utente immette la riga per i nuovi record. Quando il codice gestisce questo evento, è possibile popolare le celle desiderate con i valori desiderati.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come specificare i valori predefiniti per le nuove righe utilizzando l' <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- `NewCustomerId`Funzione per la generazione di `CustomerID` valori univoci.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
