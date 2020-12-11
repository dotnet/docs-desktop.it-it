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
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Procedura: Creare pulsanti interruttore nei controlli ToolStrip

Quando un utente fa clic su un interruttore, viene visualizzato incassato e mantiene l'aspetto incassato fino a quando l'utente fa nuovamente clic sul pulsante.

## <a name="to-create-a-toggling-toolstripbutton"></a>Per creare un elemento ToolStripButton

- Usare codice come l'esempio di codice seguente. Questo codice presuppone che il form contenga un <xref:System.Windows.Forms.ToolStrip> controllo e che la <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contenga un oggetto <xref:System.Windows.Forms.ToolStripButton> denominato `toolStripButton1` . Si presuppone inoltre che si disponga di un gestore eventi denominato `toolStripButton1_CheckedChanged` .

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripButton>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
