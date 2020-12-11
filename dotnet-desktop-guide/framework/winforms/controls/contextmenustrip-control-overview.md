---
title: Cenni preliminari sul controllo ContextMenuStrip
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951191"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="aee05-102">Cenni preliminari sul controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="aee05-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="aee05-103">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo sostituisce e aggiunge funzionalità al <xref:System.Windows.Forms.ContextMenu> controllo; tuttavia, il <xref:System.Windows.Forms.ContextMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="aee05-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="aee05-104">I menu di scelta rapida, detti anche menu di scelta rapida, vengono visualizzati nella posizione del mouse quando l'utente fa clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="aee05-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="aee05-105">I *menu* di scelta rapida forniscono le opzioni per l'area client o il controllo nella posizione del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="aee05-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="aee05-106">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo è progettato per funzionare senza problemi con i nuovi <xref:System.Windows.Forms.ToolStrip> controlli e correlati, ma è possibile associare un oggetto <xref:System.Windows.Forms.ContextMenuStrip> ad altri controlli in modo altrettanto semplice.</span><span class="sxs-lookup"><span data-stu-id="aee05-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="aee05-107">Nella tabella seguente vengono illustrate le principali <xref:System.Windows.Forms.ContextMenuStrip> classi complementari.</span><span class="sxs-lookup"><span data-stu-id="aee05-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="aee05-108">Classe</span><span class="sxs-lookup"><span data-stu-id="aee05-108">Class</span></span>|<span data-ttu-id="aee05-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aee05-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="aee05-110">Rappresenta un'opzione selezionabile visualizzata in un oggetto <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="aee05-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="aee05-111">Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco visualizzato quando l'utente fa clic su <xref:System.Windows.Forms.ToolStripDropDownButton> o su una voce di menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="aee05-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="aee05-112">Fornisce la funzionalità di base per i controlli derivati da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi a discesa quando vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="aee05-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aee05-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee05-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
