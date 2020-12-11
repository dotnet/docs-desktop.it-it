---
title: Rimuovere elementi da controlli DomainUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952032"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="afcc7-102">Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afcc7-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="afcc7-103">È possibile rimuovere elementi dal controllo Windows Forms chiamando <xref:System.Windows.Forms.DomainUpDown> il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo o della <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="afcc7-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="afcc7-104">Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo rimuove un elemento specifico, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo rimuove un elemento in base alla relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="afcc7-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="afcc7-105">Per rimuovere un elemento</span><span class="sxs-lookup"><span data-stu-id="afcc7-105">To remove an item</span></span>  
  
- <span data-ttu-id="afcc7-106">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo della <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per rimuovere un elemento in base al nome.</span><span class="sxs-lookup"><span data-stu-id="afcc7-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="afcc7-107">-oppure-</span><span class="sxs-lookup"><span data-stu-id="afcc7-107">-or-</span></span>  
  
- <span data-ttu-id="afcc7-108">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo per rimuovere un elemento in base alla relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="afcc7-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="afcc7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afcc7-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="afcc7-110">Controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="afcc7-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="afcc7-111">Panoramica del controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="afcc7-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
