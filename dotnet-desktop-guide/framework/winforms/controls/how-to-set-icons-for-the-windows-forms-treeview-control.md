---
title: Imposta icone per il controllo TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961192"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Procedura: Impostare icone per il controllo TreeView di Windows Forms
Il <xref:System.Windows.Forms.TreeView> controllo Windows Forms può visualizzare le icone accanto a ogni nodo. Le icone vengono posizionate all'estrema sinistra del testo del nodo. Per visualizzare queste icone, è necessario associare la visualizzazione ad albero a un <xref:System.Windows.Forms.ImageList> controllo. Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
> Un bug in Microsoft .NET Framework versione 1,1 impedisce che le immagini vengano visualizzate nei <xref:System.Windows.Forms.TreeView> nodi quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> . Per ovviare a questo bug, chiamare <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> nel `Main` Metodo immediatamente dopo la chiamata a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> . Questo bug è stato risolto in .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Per visualizzare le immagini in una visualizzazione albero  
  
1. Impostare la <xref:System.Windows.Forms.TreeView> proprietà del controllo sul <xref:System.Windows.Forms.TreeView.ImageList%2A> controllo esistente <xref:System.Windows.Forms.ImageList> che si desidera utilizzare.  
  
     È possibile impostare queste proprietà nella finestra di progettazione con il Finestra Proprietà o nel codice.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Impostare le <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà e del nodo <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> . La <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà determina l'immagine visualizzata per gli stati normali e espansi del nodo e la <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà determina l'immagine visualizzata per lo stato selezionato del nodo.  
  
     Queste proprietà possono essere impostate nel codice o nell'editor di TreeNode. Per aprire l'editor di TreeNode, fare clic sul pulsante con i puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà nell'finestra Proprietà.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
