---
title: 'Procedura: Abilitare il riordino di elementi ToolStrip in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964408"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Procedura: abilitare il riordino degli elementi di ToolStrip in fase di esecuzione in Windows Form
È possibile consentire all'utente di ridisporre i <xref:System.Windows.Forms.ToolStripItem> controlli in <xref:System.Windows.Forms.ToolStrip> .  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Per abilitare la riorganizzazione di ToolStripItem in fase di esecuzione  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> su `true`. Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> è `false` .  
  
     In fase di esecuzione, l'utente deve tenere premuto il tasto ALT e il pulsante sinistro del mouse per trascinare un oggetto <xref:System.Windows.Forms.ToolStripItem> in una posizione diversa in <xref:System.Windows.Forms.ToolStrip> .  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
