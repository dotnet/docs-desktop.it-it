---
title: Aggiungere elementi ai controlli DomainUpDown a livello di codice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963649"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="4d5c4-102">Procedura: aggiungere elementi ai controlli DomainUpDown Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="4d5c4-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="4d5c4-103">È possibile aggiungere elementi al controllo Windows Forms <xref:System.Windows.Forms.DomainUpDown> nel codice.</span><span class="sxs-lookup"><span data-stu-id="4d5c4-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="4d5c4-104">Chiamare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo o della <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per aggiungere elementi alla proprietà del controllo <xref:System.Windows.Forms.DomainUpDown.Items%2A> .</span><span class="sxs-lookup"><span data-stu-id="4d5c4-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="4d5c4-105">Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo aggiunge un elemento alla fine di una raccolta, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo aggiunge un elemento in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="4d5c4-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="4d5c4-106">Per aggiungere un nuovo elemento</span><span class="sxs-lookup"><span data-stu-id="4d5c4-106">To add a new item</span></span>  
  
1. <span data-ttu-id="4d5c4-107">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo per aggiungere un elemento alla fine dell'elenco di elementi.</span><span class="sxs-lookup"><span data-stu-id="4d5c4-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="4d5c4-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4d5c4-108">-or-</span></span>  
  
2. <span data-ttu-id="4d5c4-109">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per inserire un elemento nell'elenco in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="4d5c4-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d5c4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d5c4-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4d5c4-111">Controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="4d5c4-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="4d5c4-112">Panoramica del controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="4d5c4-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
