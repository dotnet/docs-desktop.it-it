---
title: 'Procedura: ottenere o impostare un valore Dock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964804"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="0f0da-102">Procedura: ottenere o impostare un valore Dock</span><span class="sxs-lookup"><span data-stu-id="0f0da-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="0f0da-103">Nell'esempio seguente viene illustrato come assegnare un <xref:System.Windows.Controls.Dock> valore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0f0da-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="0f0da-104">Nell'esempio vengono utilizzati <xref:System.Windows.Controls.DockPanel.GetDock%2A> i <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi e di <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="0f0da-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0da-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f0da-105">Example</span></span>  
 <span data-ttu-id="0f0da-106">Nell'esempio viene creata un'istanza dell' <xref:System.Windows.Controls.TextBlock> elemento, `txt1` , e viene assegnato un <xref:System.Windows.Controls.Dock> valore di utilizzando `Top` il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo di <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="0f0da-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="0f0da-107">Viene quindi aggiunto il valore della <xref:System.Windows.Controls.Dock> proprietà a <xref:System.Windows.Controls.TextBlock.Text%2A> dell' <xref:System.Windows.Controls.TextBlock> elemento utilizzando il <xref:System.Windows.Controls.DockPanel.GetDock%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="0f0da-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="0f0da-108">Infine, l'elemento viene aggiunto <xref:System.Windows.Controls.TextBlock> all'elemento padre <xref:System.Windows.Controls.DockPanel> `dp1` .</span><span class="sxs-lookup"><span data-stu-id="0f0da-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0f0da-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f0da-109">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="0f0da-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="0f0da-110">Panels Overview</span></span>](panels-overview.md)
