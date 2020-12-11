---
title: 'Procedura: Nascondere ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963784"
---
# <a name="how-to-hide-toolstripmenuitems"></a>Procedura: Nascondere ToolStripMenuItems
Nascondere le voci di menu è un modo per controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente. Spesso è necessario nascondere un intero menu quando tutte le voci di menu non sono disponibili. Questa operazione presenta un minor numero di distrazioni per l'utente. Inoltre, potrebbe essere necessario nascondere e disabilitare il menu o la voce di menu, perché nascondersi da solo non impedisce all'utente di accedere a un comando di menu utilizzando un tasto di scelta rapida.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>Per nascondere una voce di menu a livello di codice  
  
- All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere il codice su cui impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false` .  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
- [Procedura: Disabilitare ToolStripMenuItems](how-to-disable-toolstripmenuitems.md)
