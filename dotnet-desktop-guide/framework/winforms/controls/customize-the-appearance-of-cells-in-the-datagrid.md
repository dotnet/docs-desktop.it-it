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
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="57a18-102">Procedura: personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="57a18-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="57a18-103">È possibile personalizzare l'aspetto di una cella gestendo l' <xref:System.Windows.Forms.DataGridView> evento del controllo <xref:System.Windows.Forms.DataGridView.CellPainting> .</span><span class="sxs-lookup"><span data-stu-id="57a18-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="57a18-104">È possibile estrarre il <xref:System.Windows.Forms.DataGridView> controllo <xref:System.Drawing.Graphics> dalla <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="57a18-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="57a18-105">In questo <xref:System.Drawing.Graphics> modo, è possibile influire sull'aspetto dell'intero <xref:System.Windows.Forms.DataGridView> controllo, ma in genere si desidera influire solo sull'aspetto della cella attualmente disegnata.</span><span class="sxs-lookup"><span data-stu-id="57a18-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="57a18-106">La <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno alla cella attualmente disegnata.</span><span class="sxs-lookup"><span data-stu-id="57a18-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="57a18-107">Nell'esempio di codice seguente, tutte le celle di una colonna vengono disegnate `ContactName` utilizzando la <xref:System.Windows.Forms.DataGridView> combinazione di colori del controllo.</span><span class="sxs-lookup"><span data-stu-id="57a18-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="57a18-108">Il contenuto di testo di ogni cella viene <xref:System.Drawing.Color.Crimson%2A> disegnato in e un rettangolo di inserimento viene disegnato nello stesso colore della <xref:System.Windows.Forms.DataGridView> proprietà del controllo <xref:System.Windows.Forms.DataGridView.GridColor%2A> .</span><span class="sxs-lookup"><span data-stu-id="57a18-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57a18-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="57a18-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57a18-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="57a18-110">Compiling the Code</span></span>  
 <span data-ttu-id="57a18-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="57a18-111">This example requires:</span></span>  
  
- <span data-ttu-id="57a18-112">Un <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` con una `ContactName` colonna come quella nella tabella Customers del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="57a18-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="57a18-113">Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="57a18-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a18-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57a18-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="57a18-115">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="57a18-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
