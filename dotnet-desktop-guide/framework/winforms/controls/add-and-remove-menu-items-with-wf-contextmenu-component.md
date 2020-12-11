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
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="4dc74-102">Procedura: Aggiungere e rimuovere voci di menu con il componente ContextMenu di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4dc74-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="4dc74-103">Viene illustrato come aggiungere e rimuovere voci di menu di scelta rapida in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4dc74-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="4dc74-104">Il <xref:System.Windows.Forms.ContextMenu> componente Windows Forms fornisce un menu dei comandi utilizzati di frequente che sono rilevanti per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="4dc74-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="4dc74-105">È possibile aggiungere elementi al menu di scelta rapida aggiungendo <xref:System.Windows.Forms.MenuItem> oggetti alla <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="4dc74-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="4dc74-106">È possibile rimuovere elementi da un menu di scelta rapida in modo permanente; Tuttavia, in fase di esecuzione può essere più appropriato nascondere o disabilitare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="4dc74-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4dc74-107">Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controlli e delle versioni precedenti <xref:System.Windows.Forms.MainMenu> e vengono conservati per compatibilità con le versioni precedenti <xref:System.Windows.Forms.ContextMenu> e per un uso futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="4dc74-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="4dc74-108">Per rimuovere elementi da un menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="4dc74-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="4dc74-109">Utilizzare il <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> metodo o della <xref:System.Windows.Forms.Menu.MenuItems%2A> raccolta del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere una particolare voce di menu.</span><span class="sxs-lookup"><span data-stu-id="4dc74-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="4dc74-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4dc74-110">-or-</span></span>  
  
2. <span data-ttu-id="4dc74-111">Usare il `Clear` metodo della `MenuItems` raccolta del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere tutti gli elementi dal menu.</span><span class="sxs-lookup"><span data-stu-id="4dc74-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4dc74-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc74-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="4dc74-113">Componente ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4dc74-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="4dc74-114">Panoramica del componente ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4dc74-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
