---
title: 'Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961867"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="940b1-102">Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="940b1-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="940b1-103">È possibile limitare o ampliare i comandi che un utente può eseguire abilitando e disabilitando le voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="940b1-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="940b1-104">Le voci di menu sono abilitate per impostazione predefinita al momento della creazione, ma possono essere modificate tramite la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="940b1-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="940b1-105">È possibile modificare questa proprietà in fase di progettazione nella finestra **Proprietà** o a livello di codice impostando tale proprietà nel codice.</span><span class="sxs-lookup"><span data-stu-id="940b1-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="940b1-106">Per altre informazioni, vedere [procedura: disabilitare ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="940b1-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="940b1-107">Per disabilitare una voce di menu in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="940b1-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="940b1-108">Con la voce di menu selezionata nel form, impostare la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà su `false` .</span><span class="sxs-lookup"><span data-stu-id="940b1-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="940b1-109">La disabilitazione della prima o della voce di menu di primo livello in un menu Disattiva tutte le voci di menu contenute nel menu.</span><span class="sxs-lookup"><span data-stu-id="940b1-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="940b1-110">Analogamente, la disabilitazione di una voce di menu con voci di sottomenu Disabilita le voci di sottomenu.</span><span class="sxs-lookup"><span data-stu-id="940b1-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="940b1-111">Se tutti i comandi di un determinato menu non sono disponibili per l'utente, viene considerata una procedura di programmazione efficace per nascondere e disabilitare l'intero menu, in quanto presenta un'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="940b1-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="940b1-112">È necessario nascondere e disabilitare il menu, perché nascondersi da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="940b1-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="940b1-113">Impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello su `false` per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="940b1-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="940b1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="940b1-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="940b1-115">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="940b1-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="940b1-116">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="940b1-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
