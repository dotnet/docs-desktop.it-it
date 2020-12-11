---
title: 'Procedura: Associare un menu di scelta rapida a un nodo di TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962041"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="4fd12-102">Procedura: Associare un menu di scelta rapida a un nodo di TreeView</span><span class="sxs-lookup"><span data-stu-id="4fd12-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="4fd12-103">Il <xref:System.Windows.Forms.TreeView> controllo Windows Forms Visualizza una gerarchia di nodi, in modo analogo ai file e alle cartelle visualizzate nel riquadro sinistro di Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="4fd12-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="4fd12-104">Impostando la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire all'utente operazioni sensibili al contesto facendo clic con il pulsante destro del mouse sul <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="4fd12-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="4fd12-105">Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente a singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello personalizzato di funzionalità del menu di scelta rapida ai <xref:System.Windows.Forms.TreeView> controlli.</span><span class="sxs-lookup"><span data-stu-id="4fd12-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="4fd12-106">Per associare un menu di scelta rapida a un oggetto TreeNode a livello di codice</span><span class="sxs-lookup"><span data-stu-id="4fd12-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="4fd12-107">Creare un'istanza di un <xref:System.Windows.Forms.TreeView> controllo con le impostazioni delle proprietà appropriate, creare una radice <xref:System.Windows.Forms.TreeNode> e quindi aggiungere i sottonodi.</span><span class="sxs-lookup"><span data-stu-id="4fd12-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="4fd12-108">Creare un'istanza di un <xref:System.Windows.Forms.ContextMenuStrip> componente, quindi aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per ogni operazione che si desidera rendere disponibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4fd12-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="4fd12-109">Impostare la <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> proprietà dell'oggetto appropriato sul <xref:System.Windows.Forms.TreeNode> menu di scelta rapida creato.</span><span class="sxs-lookup"><span data-stu-id="4fd12-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="4fd12-110">Quando questa proprietà è impostata, il menu di scelta rapida viene visualizzato quando si fa clic con il pulsante destro del mouse sul nodo.</span><span class="sxs-lookup"><span data-stu-id="4fd12-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="4fd12-111">Nell'esempio di codice seguente viene creato un oggetto <xref:System.Windows.Forms.TreeView> di base e <xref:System.Windows.Forms.ContextMenuStrip> associato alla radice <xref:System.Windows.Forms.TreeNode> dell'oggetto <xref:System.Windows.Forms.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="4fd12-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="4fd12-112">È necessario personalizzare le scelte di menu per quelle adatte all'oggetto che <xref:System.Windows.Forms.TreeView> si sta sviluppando.</span><span class="sxs-lookup"><span data-stu-id="4fd12-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="4fd12-113">Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.ToolStripItem.Click> eventi per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="4fd12-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4fd12-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fd12-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="4fd12-115">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="4fd12-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
