---
title: Aggiungere e rimuovere voci di menu con il componente ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962287"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Procedura: Aggiungere e rimuovere voci di menu con il componente ContextMenu di Windows Forms
Viene illustrato come aggiungere e rimuovere voci di menu di scelta rapida in Windows Forms.  
  
 Il <xref:System.Windows.Forms.ContextMenu> componente Windows Forms fornisce un menu dei comandi utilizzati di frequente che sono rilevanti per l'oggetto selezionato. È possibile aggiungere elementi al menu di scelta rapida aggiungendo <xref:System.Windows.Forms.MenuItem> oggetti alla <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta.  
  
 È possibile rimuovere elementi da un menu di scelta rapida in modo permanente; Tuttavia, in fase di esecuzione può essere più appropriato nascondere o disabilitare gli elementi.  
  
> [!IMPORTANT]
> Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controlli e delle versioni precedenti <xref:System.Windows.Forms.MainMenu> e vengono conservati per compatibilità con le versioni precedenti <xref:System.Windows.Forms.ContextMenu> e per un uso futuro, se si sceglie.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Per rimuovere elementi da un menu di scelta rapida  
  
1. Utilizzare il <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> metodo o della <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere una particolare voce di menu.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     -oppure-  
  
2. Usare il `Clear` metodo della `MenuItems` raccolta del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere tutti gli elementi dal menu.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenu>
- [Componente ContextMenu](contextmenu-component-windows-forms.md)
- [Panoramica del componente ContextMenu](contextmenu-component-overview-windows-forms.md)
