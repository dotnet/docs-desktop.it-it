---
title: 'Procedura: Riassegnare i controlli esistenti a un elemento padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1767fcff1742f4ad630b4b996c709b7ded53a129
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952043"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedura: riassegnare i controlli esistenti a un padre diverso

È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.

1. In Visual Studio trascinare tre <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form. Posizionarli uno accanto a altro, ma lasciarli non allineati.

2. Nella **Casella degli strumenti** fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Non trascinare l'icona nel form.

3. Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .

   Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.

4. Fare clic e tenere premuto il pulsante del mouse.

5. Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

6. Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .

7. Rilasciare il pulsante del mouse.

   I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
