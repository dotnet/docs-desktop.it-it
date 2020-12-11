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
# <a name="how-to-create-a-complex-grid"></a>Come creare una griglia complessa

Questo esempio illustra come usare un <xref:System.Windows.Controls.Grid> controllo per creare un layout simile a un calendario mensile.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono definite otto righe e otto colonne utilizzando le <xref:System.Windows.Controls.RowDefinition> <xref:System.Windows.Controls.ColumnDefinition> classi e. Usa le <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> proprietà associate e, insieme agli <xref:System.Windows.Shapes.Rectangle> elementi, che riempiono gli sfondi di varie colonne e righe. Questa progettazione è possibile in quanto può esistere più di un elemento in ogni cella di un <xref:System.Windows.Controls.Grid> , una differenza principale tra <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table> .

Nell'esempio vengono utilizzate le sfumature verticali per <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e le righe per migliorare la presentazione visiva e la leggibilità del calendario. <xref:System.Windows.Controls.TextBlock>Gli elementi con stile rappresentano le date e i giorni della settimana. <xref:System.Windows.Controls.TextBlock> gli elementi vengono posizionati in modo assoluto all'interno delle celle usando le proprietà di <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e allineamento definite all'interno dello stile per l'applicazione.

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

La figura seguente mostra il controllo risultante, un calendario personalizzabile:

![Screenshot del controllo risultante](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Cenni preliminari sull'elemento Table](../advanced/table-overview.md)
