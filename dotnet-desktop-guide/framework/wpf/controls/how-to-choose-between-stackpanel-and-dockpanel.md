---
title: 'Procedura: scegliere tra StackPanel e DockPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: bdf4b38e67a7856136224368e86609c135e5ad6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969505"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="752f6-102">Procedura: scegliere tra StackPanel e DockPanel</span><span class="sxs-lookup"><span data-stu-id="752f6-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="752f6-103">Questo esempio illustra come scegliere se usare un oggetto <xref:System.Windows.Controls.StackPanel> o un oggetto <xref:System.Windows.Controls.DockPanel> quando si esegue lo stack del contenuto in un oggetto <xref:System.Windows.Controls.Panel> .</span><span class="sxs-lookup"><span data-stu-id="752f6-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>

## <a name="example"></a><span data-ttu-id="752f6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="752f6-104">Example</span></span>
 <span data-ttu-id="752f6-105">Sebbene sia possibile utilizzare <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> per impilare gli elementi figlio, i due controlli non producono sempre gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="752f6-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="752f6-106">Ad esempio, l'ordine in cui si inseriscono gli elementi figlio può influire sulle dimensioni degli elementi figlio in un oggetto <xref:System.Windows.Controls.DockPanel> ma non in un oggetto <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="752f6-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="752f6-107">Questo comportamento diverso si verifica perché <xref:System.Windows.Controls.StackPanel> le misure nella direzione dello stack in [Double. PositiveInfinity](xref:System.Double.PositiveInfinity), tuttavia, <xref:System.Windows.Controls.DockPanel> misurano solo le dimensioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="752f6-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at [Double.PositiveInfinity](xref:System.Double.PositiveInfinity); however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>

 <span data-ttu-id="752f6-108">Nell'esempio seguente viene illustrata la differenza principale tra <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="752f6-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="752f6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="752f6-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="752f6-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="752f6-110">Panels Overview</span></span>](panels-overview.md)
