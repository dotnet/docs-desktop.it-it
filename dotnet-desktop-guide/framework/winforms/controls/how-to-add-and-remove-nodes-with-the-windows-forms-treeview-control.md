---
title: Aggiungere e rimuovere nodi con il controllo TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962116"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms
Il <xref:System.Windows.Forms.TreeView> controllo Windows Forms archivia i nodi di primo livello nella relativa <xref:System.Windows.Forms.TreeView.Nodes%2A> raccolta. Ogni <xref:System.Windows.Forms.TreeNode> dispone anche di una propria <xref:System.Windows.Forms.TreeNode.Nodes%2A> raccolta per archiviare i relativi nodi figlio. Entrambe le proprietà della raccolta sono di tipo <xref:System.Windows.Forms.TreeNodeCollection> , che fornisce membri della raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi a un singolo livello della gerarchia del nodo.  
  
### <a name="to-add-nodes-programmatically"></a>Per aggiungere nodi a livello di codice  
  
1. Utilizzare il <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> metodo della proprietà della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> .  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a>Per rimuovere i nodi a livello di codice  
  
1. Usare il <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> metodo della proprietà della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> per rimuovere un singolo nodo o il <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> metodo per cancellare tutti i nodi.  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica del controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Impostare icone per il controllo TreeView di Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
