---
title: Come creare una griglia complessa
description: Esempio di utilizzo di un controllo Grid per creare un layout simile a un calendario mensile.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: ab5490d608b21fe8b29a078dc1f0147f038c27a3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969472"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="a570f-103">Come creare una griglia complessa</span><span class="sxs-lookup"><span data-stu-id="a570f-103">How to create a complex Grid</span></span>

<span data-ttu-id="a570f-104">Questo esempio illustra come usare un <xref:System.Windows.Controls.Grid> controllo per creare un layout simile a un calendario mensile.</span><span class="sxs-lookup"><span data-stu-id="a570f-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="a570f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a570f-105">Example</span></span>

<span data-ttu-id="a570f-106">Nell'esempio seguente vengono definite otto righe e otto colonne utilizzando le <xref:System.Windows.Controls.RowDefinition> <xref:System.Windows.Controls.ColumnDefinition> classi e.</span><span class="sxs-lookup"><span data-stu-id="a570f-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="a570f-107">Usa le <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> proprietà associate e, insieme agli <xref:System.Windows.Shapes.Rectangle> elementi, che riempiono gli sfondi di varie colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="a570f-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="a570f-108">Questa progettazione è possibile in quanto può esistere più di un elemento in ogni cella di un <xref:System.Windows.Controls.Grid> , una differenza principale tra <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table> .</span><span class="sxs-lookup"><span data-stu-id="a570f-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="a570f-109">Nell'esempio vengono utilizzate le sfumature verticali per <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e le righe per migliorare la presentazione visiva e la leggibilità del calendario.</span><span class="sxs-lookup"><span data-stu-id="a570f-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="a570f-110"><xref:System.Windows.Controls.TextBlock>Gli elementi con stile rappresentano le date e i giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="a570f-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="a570f-111"><xref:System.Windows.Controls.TextBlock> gli elementi vengono posizionati in modo assoluto all'interno delle celle usando le proprietà di <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e allineamento definite all'interno dello stile per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a570f-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="a570f-112">La figura seguente mostra il controllo risultante, un calendario personalizzabile:</span><span class="sxs-lookup"><span data-stu-id="a570f-112">The following image shows the resulting control, a customizable calendar:</span></span>

![Screenshot del controllo risultante](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="a570f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a570f-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="a570f-115">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="a570f-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="a570f-116">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="a570f-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="a570f-117">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="a570f-117">Table Overview</span></span>](../advanced/table-overview.md)
