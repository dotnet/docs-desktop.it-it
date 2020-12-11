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
# <a name="how-to-get-or-set-a-dock-value"></a>Procedura: ottenere o impostare un valore Dock
Nell'esempio seguente viene illustrato come assegnare un <xref:System.Windows.Controls.Dock> valore per un oggetto. Nell'esempio vengono utilizzati <xref:System.Windows.Controls.DockPanel.GetDock%2A> i <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi e di <xref:System.Windows.Controls.DockPanel> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene creata un'istanza dell' <xref:System.Windows.Controls.TextBlock> elemento, `txt1` , e viene assegnato un <xref:System.Windows.Controls.Dock> valore di utilizzando `Top` il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo di <xref:System.Windows.Controls.DockPanel> . Viene quindi aggiunto il valore della <xref:System.Windows.Controls.Dock> proprietà a <xref:System.Windows.Controls.TextBlock.Text%2A> dell' <xref:System.Windows.Controls.TextBlock> elemento utilizzando il <xref:System.Windows.Controls.DockPanel.GetDock%2A> metodo. Infine, l'elemento viene aggiunto <xref:System.Windows.Controls.TextBlock> all'elemento padre <xref:System.Windows.Controls.DockPanel> `dp1` .  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
