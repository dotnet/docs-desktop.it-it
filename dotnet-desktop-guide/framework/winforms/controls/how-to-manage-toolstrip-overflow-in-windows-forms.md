---
title: "Procedura: Gestire l'overflow di ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952092"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Procedura: gestire l'overflow di ToolStrip in Windows Form

Quando tutti gli elementi di un <xref:System.Windows.Forms.ToolStrip> controllo non rientrano nello spazio assegnato, è possibile abilitare la funzionalità di overflow su <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di specifici <xref:System.Windows.Forms.ToolStripItem> .

Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem> che richiedono più spazio rispetto a quello assegnato a <xref:System.Windows.Forms.ToolStrip> , date le dimensioni correnti del modulo, <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato automaticamente un oggetto in <xref:System.Windows.Forms.ToolStrip> . Il <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato e gli elementi abilitati per l'overflow vengono spostati nel menu a discesa di overflow. In questo modo è possibile personalizzare e definire le priorità <xref:System.Windows.Forms.ToolStrip> per adattare correttamente gli elementi alle diverse dimensioni del modulo. È anche possibile modificare l'aspetto degli elementi quando rientrano nell'overflow usando le <xref:System.Windows.Forms.ToolStripItem.Placement%2A> <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> proprietà e e l' <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento. Se si ingrandisce il form in fase di progettazione o in fase di esecuzione, è possibile visualizzare più istanze di nel <xref:System.Windows.Forms.ToolStripItem> Main <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbe addirittura scomparire fino a quando non si diminuiscono le dimensioni del form.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>Per abilitare l'overflow su un controllo ToolStrip

- Verificare che la <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> proprietà non sia impostata su `false` per <xref:System.Windows.Forms.ToolStrip> . Il valore predefinito è `True`.

     Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> è `True` (impostazione predefinita), un oggetto <xref:System.Windows.Forms.ToolStripItem> viene inviato al menu a discesa di overflow quando il contenuto dell'oggetto <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un oggetto orizzontale <xref:System.Windows.Forms.ToolStrip> o l'altezza di un oggetto verticale <xref:System.Windows.Forms.ToolStrip> .

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Per specificare il comportamento di overflow di un oggetto ToolStripItem specifico

- Impostare la <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> proprietà di sul <xref:System.Windows.Forms.ToolStripItem> valore desiderato. Le possibilità sono `Always` , `Never` e `AsNeeded` . Il valore predefinito è `AsNeeded`.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
