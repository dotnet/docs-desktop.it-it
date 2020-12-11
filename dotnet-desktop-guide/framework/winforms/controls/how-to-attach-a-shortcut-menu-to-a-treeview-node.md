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
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Procedura: Associare un menu di scelta rapida a un nodo di TreeView
Il <xref:System.Windows.Forms.TreeView> controllo Windows Forms Visualizza una gerarchia di nodi, in modo analogo ai file e alle cartelle visualizzate nel riquadro sinistro di Esplora risorse. Impostando la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire all'utente operazioni sensibili al contesto facendo clic con il pulsante destro del mouse sul <xref:System.Windows.Forms.TreeView> controllo. Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente a singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello personalizzato di funzionalità del menu di scelta rapida ai <xref:System.Windows.Forms.TreeView> controlli.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Per associare un menu di scelta rapida a un oggetto TreeNode a livello di codice  
  
1. Creare un'istanza di un <xref:System.Windows.Forms.TreeView> controllo con le impostazioni delle proprietà appropriate, creare una radice <xref:System.Windows.Forms.TreeNode> e quindi aggiungere i sottonodi.  
  
2. Creare un'istanza di un <xref:System.Windows.Forms.ContextMenuStrip> componente, quindi aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per ogni operazione che si desidera rendere disponibile in fase di esecuzione.  
  
3. Impostare la <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> proprietà dell'oggetto appropriato sul <xref:System.Windows.Forms.TreeNode> menu di scelta rapida creato.  
  
4. Quando questa proprietà è impostata, il menu di scelta rapida viene visualizzato quando si fa clic con il pulsante destro del mouse sul nodo.  
  
 Nell'esempio di codice seguente viene creato un oggetto <xref:System.Windows.Forms.TreeView> di base e <xref:System.Windows.Forms.ContextMenuStrip> associato alla radice <xref:System.Windows.Forms.TreeNode> dell'oggetto <xref:System.Windows.Forms.TreeView> . È necessario personalizzare le scelte di menu per quelle adatte all'oggetto che <xref:System.Windows.Forms.TreeView> si sta sviluppando. Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.ToolStripItem.Click> eventi per queste voci di menu.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenuStrip>
- [Controllo TreeView](treeview-control-windows-forms.md)
