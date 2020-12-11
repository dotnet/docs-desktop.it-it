---
title: "Procedura: modificare la spaziatura e l'allineamento degli elementi ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963949"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Procedura: Modificare la spaziatura e l'allineamento degli elementi ToolStrip in Windows Forms
Il <xref:System.Windows.Forms.ToolStrip> controllo supporta completamente le funzionalità di layout, ad esempio il ridimensionamento, la spaziatura dei <xref:System.Windows.Forms.ToolStripItem> controlli relativi tra loro, la disposizione dei controlli in <xref:System.Windows.Forms.ToolStrip> e la spaziatura dei controlli relativi a <xref:System.Windows.Forms.ToolStrip> .  
  
 Poiché il valore predefinito della <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà è `true` , i controlli vengono ridimensionati automaticamente a meno che non si imposti la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà su `false` .  
  
### <a name="to-manually-size-a-toolstripitem"></a>Per ridimensionare manualmente un oggetto ToolStripItem  
  
1. Impostare la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> proprietà su `false` per il controllo associato.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Impostare la <xref:System.Windows.Forms.ToolStripItem.Size%2A> proprietà nel modo desiderato per l'oggetto associato <xref:System.Windows.Forms.ToolStripItem> .  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Per impostare la spaziatura di un oggetto ToolStripItem  
  
1. Inserire i valori desiderati, in pixel, nella <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà del controllo associato.  
  
     I valori della <xref:System.Windows.Forms.ToolStripItem.Margin%2A> proprietà specificano la spaziatura tra l'elemento e gli elementi adiacenti in questo ordine: Left, top, Right e Bottom.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Per allineare un oggetto ToolStripItem al lato destro di ToolStrip  
  
1. Impostare la <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà su <xref:System.Windows.Forms.ToolStripItemAlignment.Right> per il controllo associato. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> è impostato su <xref:System.Windows.Forms.ToolStripItemAlignment.Left> , che allinea i controlli al lato sinistro di <xref:System.Windows.Forms.ToolStrip> .  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Per disporre gli elementi ToolStrip in ToolStrip  
  
- Impostare la <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> proprietà sul valore <xref:System.Windows.Forms.ToolStripLayoutStyle> desiderato.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
