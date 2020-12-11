---
title: 'Procedura: Abilitare il completamento automatico nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961816"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Procedura: abilitare il completamento automatico nei controlli ToolStrip Windows Form
La procedura seguente combina un <xref:System.Windows.Forms.ToolStripLabel> con un <xref:System.Windows.Forms.ToolStripComboBox> che può essere rilasciato per visualizzare un elenco di elementi, ad esempio siti Web visitati di recente. Se l'utente digita un carattere che corrisponde al primo carattere di uno degli elementi dell'elenco, l'elemento viene immediatamente visualizzato.  
  
> [!NOTE]
> Il completamento automatico funziona con `ToolStrip` i controlli nello stesso modo in cui funziona con i controlli tradizionali, ad esempio <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.TextBox> .  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>Per abilitare il completamento automatico in un controllo ToolStrip  
  
1. Creare un <xref:System.Windows.Forms.ToolStrip> controllo e aggiungervi elementi.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. Impostare la <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> proprietà dell'etichetta e della casella combinata su in <xref:System.Windows.Forms.ToolStripItemOverflow.Never> modo che l'elenco sia sempre disponibile indipendentemente dalle dimensioni del form.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. Aggiungere parole alla raccolta Items del <xref:System.Windows.Forms.ToolStripComboBox> controllo.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Impostare la <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> proprietà della casella combinata su <xref:System.Windows.Forms.AutoCompleteMode.Append> .  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Impostare la <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> proprietà della casella combinata su <xref:System.Windows.Forms.AutoCompleteSource.ListItems> .  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
