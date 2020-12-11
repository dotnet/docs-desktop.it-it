---
title: Personalizzare l'aspetto delle celle nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951123"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Procedura: personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form
È possibile personalizzare l'aspetto di una cella gestendo l' <xref:System.Windows.Forms.DataGridView> evento del controllo <xref:System.Windows.Forms.DataGridView.CellPainting> . È possibile estrarre il <xref:System.Windows.Forms.DataGridView> controllo <xref:System.Drawing.Graphics> dalla <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> . In questo <xref:System.Drawing.Graphics> modo, è possibile influire sull'aspetto dell'intero <xref:System.Windows.Forms.DataGridView> controllo, ma in genere si desidera influire solo sull'aspetto della cella attualmente disegnata. La <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno alla cella attualmente disegnata.  
  
 Nell'esempio di codice seguente, tutte le celle di una colonna vengono disegnate `ContactName` utilizzando la <xref:System.Windows.Forms.DataGridView> combinazione di colori del controllo. Il contenuto di testo di ogni cella viene <xref:System.Drawing.Color.Crimson%2A> disegnato in e un rettangolo di inserimento viene disegnato nello stesso colore della <xref:System.Windows.Forms.DataGridView> proprietà del controllo <xref:System.Windows.Forms.DataGridView.GridColor%2A> .  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` con una `ContactName` colonna come quella nella tabella Customers del database di esempio Northwind.  
  
- Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Personalizzazione del controllo DataGridView Windows Form](customizing-the-windows-forms-datagridview-control.md)
