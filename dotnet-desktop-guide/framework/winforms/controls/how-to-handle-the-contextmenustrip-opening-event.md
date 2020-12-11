---
title: "Procedura: Gestire l'evento di apertura di ContextMenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963796"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Procedura: Gestire l'evento di apertura di ContextMenuStrip
È possibile personalizzare il comportamento del <xref:System.Windows.Forms.ContextMenuStrip> controllo gestendo l' <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come gestire l' <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento. Il gestore eventi aggiunge elementi in modo dinamico a un <xref:System.Windows.Forms.ContextMenuStrip> controllo. Per l'esempio di codice completo, vedere [procedura: aggiungere elementi ToolStrip dinamicamente](how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Impostare la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> proprietà su `true` per impedire l'apertura del menu.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
