---
title: 'Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961876"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ad596-102">Procedura: Rilevare quando il puntatore del mouse si trova sopra un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="ad596-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="ad596-103">Utilizzare la procedura seguente per rilevare quando il puntatore del mouse è posizionato su un oggetto <xref:System.Windows.Forms.ToolStripItem> .</span><span class="sxs-lookup"><span data-stu-id="ad596-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ad596-104">Per rilevare quando il puntatore è posizionato su un oggetto ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="ad596-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="ad596-105">Utilizzare la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> proprietà per gli elementi in cui <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> è `true` .</span><span class="sxs-lookup"><span data-stu-id="ad596-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="ad596-106">In questo modo si evita di dover sincronizzare gli <xref:System.Windows.Forms.ToolStripItem.MouseEnter> <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventi e.</span><span class="sxs-lookup"><span data-stu-id="ad596-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad596-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad596-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="ad596-108">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ad596-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
