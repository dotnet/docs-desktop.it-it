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
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Procedura: aggiungere elementi ai controlli DomainUpDown Windows Form a livello di codice
È possibile aggiungere elementi al controllo Windows Forms <xref:System.Windows.Forms.DomainUpDown> nel codice. Chiamare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo o della <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per aggiungere elementi alla proprietà del controllo <xref:System.Windows.Forms.DomainUpDown.Items%2A> . Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo aggiunge un elemento alla fine di una raccolta, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo aggiunge un elemento in una posizione specificata.  
  
### <a name="to-add-a-new-item"></a>Per aggiungere un nuovo elemento  
  
1. Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo per aggiungere un elemento alla fine dell'elenco di elementi.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     -oppure-  
  
2. Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per inserire un elemento nell'elenco in una posizione specificata.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [Controllo DomainUpDown](domainupdown-control-windows-forms.md)
- [Panoramica del controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)
