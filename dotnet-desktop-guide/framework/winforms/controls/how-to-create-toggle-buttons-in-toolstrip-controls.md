---
title: 'Procedura: Creare pulsanti interruttore nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963889"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="e1c5b-102">Procedura: Creare pulsanti interruttore nei controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e1c5b-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>

<span data-ttu-id="e1c5b-103">Quando un utente fa clic su un interruttore, viene visualizzato incassato e mantiene l'aspetto incassato fino a quando l'utente fa nuovamente clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>

## <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="e1c5b-104">Per creare un elemento ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="e1c5b-104">To create a toggling ToolStripButton</span></span>

- <span data-ttu-id="e1c5b-105">Usare codice come l'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e1c5b-105">Use code such as the following code example.</span></span> <span data-ttu-id="e1c5b-106">Questo codice presuppone che il form contenga un <xref:System.Windows.Forms.ToolStrip> controllo e che la <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contenga un oggetto <xref:System.Windows.Forms.ToolStripButton> denominato `toolStripButton1` .</span><span class="sxs-lookup"><span data-stu-id="e1c5b-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="e1c5b-107">Si presuppone inoltre che si disponga di un gestore eventi denominato `toolStripButton1_CheckedChanged` .</span><span class="sxs-lookup"><span data-stu-id="e1c5b-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a><span data-ttu-id="e1c5b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1c5b-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="e1c5b-109">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e1c5b-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
