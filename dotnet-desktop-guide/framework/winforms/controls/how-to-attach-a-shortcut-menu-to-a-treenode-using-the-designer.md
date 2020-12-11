---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962044"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="1bdaf-102">Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1bdaf-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="1bdaf-103">Il <xref:System.Windows.Forms.TreeView> controllo Windows Forms Visualizza una gerarchia di nodi, in modo analogo ai file e alle cartelle visualizzati nel riquadro sinistro della funzionalità Esplora risorse nei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="1bdaf-104">Impostando la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire all'utente operazioni sensibili al contesto facendo clic con il pulsante destro del mouse sul <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1bdaf-105">Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente a singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello personalizzato di funzionalità del menu di scelta rapida ai <xref:System.Windows.Forms.TreeView> controlli.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="1bdaf-106">Per associare un menu di scelta rapida a un oggetto TreeNode in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1bdaf-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="1bdaf-107">Aggiungere un <xref:System.Windows.Forms.TreeView> controllo al form e quindi aggiungere nodi a in base alle <xref:System.Windows.Forms.TreeView> esigenze.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="1bdaf-108">Per altre informazioni, vedere [procedura: aggiungere e rimuovere nodi con il controllo TreeView Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span><span class="sxs-lookup"><span data-stu-id="1bdaf-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="1bdaf-109">Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> componente al form, quindi aggiungere voci di menu al menu di scelta rapida che rappresentano le operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="1bdaf-110">Per altre informazioni, vedere [procedura: aggiungere voci di menu a un ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span><span class="sxs-lookup"><span data-stu-id="1bdaf-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="1bdaf-111">Riaprire la finestra di dialogo **Editor TreeNode** per il <xref:System.Windows.Forms.TreeView> controllo, selezionare il nodo da modificare e impostare la relativa <xref:System.Windows.Forms.ContextMenuStrip> proprietà sul menu di scelta rapida aggiunto.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="1bdaf-112">Quando questa proprietà è impostata, il menu di scelta rapida viene visualizzato quando si fa clic con il pulsante destro del mouse sul nodo.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="1bdaf-113">Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.ToolStripItem.Click> eventi per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bdaf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bdaf-114">See also</span></span>

- [<span data-ttu-id="1bdaf-115">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="1bdaf-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="1bdaf-116">Panoramica del controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="1bdaf-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="1bdaf-117">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="1bdaf-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
