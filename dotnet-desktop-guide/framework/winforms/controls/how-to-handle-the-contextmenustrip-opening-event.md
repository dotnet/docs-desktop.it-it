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
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="8262a-102">Procedura: Gestire l'evento di apertura di ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8262a-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="8262a-103">È possibile personalizzare il comportamento del <xref:System.Windows.Forms.ContextMenuStrip> controllo gestendo l' <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento.</span><span class="sxs-lookup"><span data-stu-id="8262a-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8262a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8262a-104">Example</span></span>  
 <span data-ttu-id="8262a-105">Nell'esempio di codice riportato di seguito viene illustrato come gestire l' <xref:System.Windows.Forms.ToolStripDropDown.Opening> evento.</span><span class="sxs-lookup"><span data-stu-id="8262a-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="8262a-106">Il gestore eventi aggiunge elementi in modo dinamico a un <xref:System.Windows.Forms.ContextMenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="8262a-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="8262a-107">Per l'esempio di codice completo, vedere [procedura: aggiungere elementi ToolStrip dinamicamente](how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="8262a-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="8262a-108">Impostare la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> proprietà su `true` per impedire l'apertura del menu.</span><span class="sxs-lookup"><span data-stu-id="8262a-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8262a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8262a-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="8262a-110">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8262a-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
