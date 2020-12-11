---
title: Panoramica del componente MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961534"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="40eff-102">Cenni preliminari sul componente MainMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="40eff-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="40eff-103">Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controlli e delle versioni precedenti <xref:System.Windows.Forms.MainMenu> e vengono conservati per compatibilità con le versioni precedenti <xref:System.Windows.Forms.ContextMenu> e per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="40eff-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="40eff-104">Il <xref:System.Windows.Forms.MainMenu> componente Windows Forms Visualizza un menu in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="40eff-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="40eff-105">Tutti i sottomenu del menu principale e dei singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="40eff-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="40eff-106">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="40eff-106">Key Properties</span></span>  
 <span data-ttu-id="40eff-107">Una voce di menu può essere designata come elemento predefinito impostando la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="40eff-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="40eff-108">Quando si fa clic sul menu, l'elemento predefinito viene visualizzato in grassetto.</span><span class="sxs-lookup"><span data-stu-id="40eff-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="40eff-109">La proprietà della voce di menu <xref:System.Windows.Forms.MenuItem.Checked%2A> può essere `true` o `false` e indica se la voce di menu è selezionata.</span><span class="sxs-lookup"><span data-stu-id="40eff-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="40eff-110">La proprietà della voce <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> di menu Personalizza l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `true` , accanto all'elemento viene visualizzato un pulsante di opzione; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false` , accanto all'elemento viene visualizzato un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="40eff-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eff-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40eff-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="40eff-112">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="40eff-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
