---
title: 'Procedura: Spostare ToolStrip da ToolStripContainer a un modulo'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: c6519add6789485d41146633abb5e11f80913649
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961741"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Procedura: Spostare ToolStrip da ToolStripContainer a un modulo
Utilizzare la procedura seguente per spostare un oggetto <xref:System.Windows.Forms.ToolStrip> da un oggetto in <xref:System.Windows.Forms.ToolStripContainer> un form.

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Per spostare un controllo ToolStrip da un oggetto ToolStripContainer a un form

1. Selezionare <xref:System.Windows.Forms.ToolStrip>.

2. Tagliare <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X oppure facendo clic con il pulsante destro del mouse <xref:System.Windows.Forms.ToolStrip> e scegliendo **taglia** dal menu di scelta rapida.

3. Selezionare il modulo.

4. Incollare <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V o scegliendo **Incolla** dal menu **modifica** .

5. Impostare la <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà dell'oggetto <xref:System.Windows.Forms.ToolStrip> su **Top**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
