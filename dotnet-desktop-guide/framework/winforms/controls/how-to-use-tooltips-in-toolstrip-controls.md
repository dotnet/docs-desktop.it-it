---
title: 'Procedura: Usare le descrizioni comando nei controlli ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965155"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="3d2e7-102">Procedura: Usare le descrizioni comando nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3d2e7-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="3d2e7-103">È possibile visualizzare un oggetto <xref:System.Windows.Forms.ToolTip> per il <xref:System.Windows.Forms.ToolStrip> controllo desiderato impostando la proprietà del controllo <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> su `true` .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="3d2e7-104">Per visualizzare una descrizione comando</span><span class="sxs-lookup"><span data-stu-id="3d2e7-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="3d2e7-105">Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del controllo su `true` .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="3d2e7-106">Il valore predefinito di <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è e `true` il valore predefinito di <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> è `false` .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="3d2e7-107">Per utilizzare la proprietà ToolTipText per il testo della descrizione comando di un oggetto ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="3d2e7-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="3d2e7-108">Impostare la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> proprietà del pulsante su `true` .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="3d2e7-109">Impostare la <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> proprietà del pulsante su `false` .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="3d2e7-110">`AutoToolTip` `true` Per impostazione predefinita, la proprietà è per <xref:System.Windows.Forms.ToolStripButton> , <xref:System.Windows.Forms.ToolStripDropDownButton> e <xref:System.Windows.Forms.ToolStripSplitButton> .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="3d2e7-111"><xref:System.Windows.Forms.ToolStripButton> `Text` Per impostazione predefinita, usa la proprietà per il <xref:System.Windows.Forms.ToolTip> testo.</span><span class="sxs-lookup"><span data-stu-id="3d2e7-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="3d2e7-112">Usare questa procedura per visualizzare il testo personalizzato in un oggetto <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> .</span><span class="sxs-lookup"><span data-stu-id="3d2e7-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d2e7-113">Se si imposta <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> su o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image> , non verrà visualizzato alcun testo sul pulsante, ma verrà ancora visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="3d2e7-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2e7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d2e7-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="3d2e7-115">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3d2e7-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
