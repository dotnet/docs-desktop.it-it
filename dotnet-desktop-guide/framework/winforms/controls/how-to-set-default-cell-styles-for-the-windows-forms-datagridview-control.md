---
title: Impostare gli stili di cella predefiniti per il controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 6b2d7de671e48ae8f55987c262e15717138b3fb4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951996"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="e77b7-102">Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e77b7-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e77b7-103">Con il controllo <xref:System.Windows.Forms.DataGridView> è possibile specificare gli stili di cella predefiniti per l'intero controllo e per specifiche colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="e77b7-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="e77b7-104">Queste impostazioni predefinite filtrano dal livello di controllo al livello di colonna, quindi al livello di riga e infine di cella.</span><span class="sxs-lookup"><span data-stu-id="e77b7-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="e77b7-105">Se una particolare proprietà <xref:System.Windows.Forms.DataGridViewCellStyle> non è impostata a livello di cella, viene usata l'impostazione predefinita della proprietà a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="e77b7-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="e77b7-106">Se la proprietà non è impostata neanche a livello di riga, viene usata l'impostazione predefinita della colonna.</span><span class="sxs-lookup"><span data-stu-id="e77b7-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="e77b7-107">Infine, se la proprietà non è impostata neanche a livello di colonna, viene usata l'impostazione predefinita <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e77b7-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="e77b7-108">Con questa impostazione è possibile evitare di duplicare le impostazioni della proprietà a più livelli.</span><span class="sxs-lookup"><span data-stu-id="e77b7-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="e77b7-109">A ogni livello è sufficiente specificare gli stili che differiscono dai livelli superiori.</span><span class="sxs-lookup"><span data-stu-id="e77b7-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="e77b7-110">Per ulteriori informazioni, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="e77b7-111">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="e77b7-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="e77b7-112">Vedere anche [procedura: impostare stili di cella e formati di dati predefiniti per il controllo DataGridView Windows Forms usando la finestra di progettazione](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="e77b7-113">Per impostare gli stili della cella predefiniti a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e77b7-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="e77b7-114">Impostare le proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellStyle> recuperato tramite la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e77b7-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="e77b7-115">Creare e inizializzare nuovi oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> per l'uso da più righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="e77b7-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="e77b7-116">Impostare la proprietà `DefaultCellStyle` di righe e colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="e77b7-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="e77b7-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="e77b7-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e77b7-118">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e77b7-118">Compiling the Code</span></span>  
 <span data-ttu-id="e77b7-119">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e77b7-119">This example requires:</span></span>  
  
- <span data-ttu-id="e77b7-120">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="e77b7-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="e77b7-121">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e77b7-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e77b7-122">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e77b7-122">Robust Programming</span></span>  
 <span data-ttu-id="e77b7-123">Per ottenere la massima scalabilità quando si lavora con set di dati molto grandi, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per i singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="e77b7-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="e77b7-124">È anche necessario creare righe condivise e accedervi mediante la proprietà <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e77b7-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e77b7-125">Per altre informazioni, vedere [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77b7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e77b7-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e77b7-127">Formattazione e stile di base nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e77b7-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e77b7-128">Stili della cella nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e77b7-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e77b7-129">Procedure consigliate per ridimensionare il controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e77b7-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e77b7-130">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e77b7-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
