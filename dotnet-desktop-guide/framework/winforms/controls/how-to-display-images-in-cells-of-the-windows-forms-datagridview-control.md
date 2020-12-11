---
title: Visualizzare immagini in celle del controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961858"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Procedura: Visualizzare immagini nelle celle del controllo DataGridView di Windows Forms
Un'immagine o un elemento grafico è uno dei valori che è possibile visualizzare in una riga di dati. Spesso, questi elementi grafici hanno il formato di una fotografia di un dipendente o di un logo aziendale.  
  
 L'incorporamento di immagini è semplice quando si visualizzano i dati all'interno del <xref:System.Windows.Forms.DataGridView> controllo. Il <xref:System.Windows.Forms.DataGridView> controllo gestisce in modo nativo qualsiasi formato di immagine supportato dalla <xref:System.Drawing.Image> classe, nonché il formato immagine OLE utilizzato da alcuni database.  
  
 Se l' <xref:System.Windows.Forms.DataGridView> origine dati del controllo include una colonna di immagini, queste verranno visualizzate automaticamente dal <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come estrarre un'icona da una risorsa incorporata e convertirla in una bitmap per la visualizzazione in ogni cella di una colonna di un'immagine. Per un altro esempio che sostituisce i valori di cella testuale con le immagini corrispondenti, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Risorsa di icona incorporata denominata `tree.ico` .  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
