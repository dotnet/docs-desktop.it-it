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
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="3cebe-102">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3cebe-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="3cebe-103">Nascondere le voci di menu è un modo per controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cebe-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="3cebe-104">Spesso è necessario nascondere un intero menu quando tutte le voci di menu non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="3cebe-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="3cebe-105">Questa operazione presenta un minor numero di distrazioni per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3cebe-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="3cebe-106">Inoltre, potrebbe essere necessario nascondere e disabilitare il menu o la voce di menu, perché nascondersi da solo non impedisce all'utente di accedere a un comando di menu utilizzando un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3cebe-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="3cebe-107">Per nascondere una voce di menu a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3cebe-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="3cebe-108">All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere il codice su cui impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà `false` .</span><span class="sxs-lookup"><span data-stu-id="3cebe-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3cebe-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cebe-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="3cebe-110">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3cebe-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="3cebe-111">Procedura: Disabilitare ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3cebe-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
