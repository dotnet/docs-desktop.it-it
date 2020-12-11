---
title: 'Procedura: Individuare il nodo di TreeView scelto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963838"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Procedura: individuare il nodo di TreeView scelto (Windows Form)
Quando si utilizza il <xref:System.Windows.Forms.TreeView> controllo Windows Forms, un'attività comune consiste nel determinare il nodo selezionato e rispondere in modo appropriato.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Per determinare quale nodo di TreeView è stato selezionato  
  
1. Utilizzare l' <xref:System.EventArgs> oggetto per restituire un riferimento all'oggetto nodo selezionato.  
  
2. Determinare su quale nodo è stato fatto clic controllando la <xref:System.Windows.Forms.TreeViewEventArgs> classe, che contiene i dati relativi all'evento.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    > In alternativa, è possibile usare l'oggetto <xref:System.Windows.Forms.MouseEventArgs> dell' <xref:System.Windows.Forms.Control.MouseDown> evento o <xref:System.Windows.Forms.Control.MouseUp> per ottenere i <xref:System.Drawing.Point.X%2A> valori della <xref:System.Drawing.Point.Y%2A> coordinata e dell'oggetto in <xref:System.Drawing.Point> cui si è verificato il clic. Usare quindi il <xref:System.Windows.Forms.TreeView> metodo del controllo <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> per determinare su quale nodo è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
