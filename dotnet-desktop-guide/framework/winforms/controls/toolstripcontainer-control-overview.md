---
title: Cenni preliminari sul controllo ToolStripContainer
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966565"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="0b34c-102">Cenni preliminari sul controllo ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="0b34c-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="0b34c-103">Un oggetto <xref:System.Windows.Forms.ToolStripContainer> dispone di pannelli sui lati sinistro, destro, superiore e inferiore per il posizionamento e il raggruppamento di <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> controlli, e <xref:System.Windows.Forms.StatusStrip> .</span><span class="sxs-lookup"><span data-stu-id="0b34c-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="0b34c-104">Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra.</span><span class="sxs-lookup"><span data-stu-id="0b34c-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="0b34c-105">Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso.</span><span class="sxs-lookup"><span data-stu-id="0b34c-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="0b34c-106">È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.</span><span class="sxs-lookup"><span data-stu-id="0b34c-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="0b34c-107">Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="0b34c-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="0b34c-108">Ogni pannello di un <xref:System.Windows.Forms.ToolStripContainer> è espandibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="0b34c-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="0b34c-109">Membri di ToolStripContainer importanti</span><span class="sxs-lookup"><span data-stu-id="0b34c-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="0b34c-110">Name</span><span class="sxs-lookup"><span data-stu-id="0b34c-110">Name</span></span>|<span data-ttu-id="0b34c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b34c-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="0b34c-112">Ottiene il pannello inferiore dell'oggetto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="0b34c-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="0b34c-113">Ottiene o imposta un valore che indica se il pannello inferiore dell'oggetto <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="0b34c-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="0b34c-114">Ottiene il pannello sinistro dell'oggetto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="0b34c-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="0b34c-115">Ottiene o imposta un valore che indica se il pannello sinistro di <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="0b34c-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="0b34c-116">Ottiene il pannello destro di <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="0b34c-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="0b34c-117">Ottiene o imposta un valore che indica se il pannello destro di <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="0b34c-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="0b34c-118">Ottiene il pannello superiore di <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="0b34c-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="0b34c-119">Ottiene o imposta un valore che indica se il pannello superiore di <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="0b34c-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b34c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b34c-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
