---
title: Ancorare i controlli (Dock)
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: c765c7e1a109a6185cca130f120d032eb0a6a3cf
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956954"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedura: ancorare i controlli in Windows Form

È possibile ancorare i controlli ai bordi del form oppure fare in modo che riempiano il contenitore del controllo, ovvero un form o un controllo contenitore. Ad esempio, Esplora risorse ancora il <xref:System.Windows.Forms.TreeView> controllo al lato sinistro della finestra e il relativo controllo sul <xref:System.Windows.Forms.ListView> lato destro della finestra. Usare la <xref:System.Windows.Forms.Control.Dock%2A> proprietà per tutti i controlli di Windows Form visibili per definire la modalità di ancoraggio.

> [!NOTE]
> I controlli sono ancorati nell'ordine z inverso.

La <xref:System.Windows.Forms.Control.Dock%2A> proprietà interagisce con la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Per ancorare un controllo

1. In Visual Studio selezionare il controllo che si desidera ancorare.

2. Nella finestra **Proprietà** fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Dock%2A> Proprietà.

   Viene visualizzato un editor che mostra una serie di caselle che rappresentano i bordi e il centro del form.

3. Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo. Per riempire il contenuto del form o del controllo contenitore del controllo, fare clic sulla casella al centro. Per disabilitare l'ancoraggio, fare clic su **(nessuno)** .

   Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.

   > [!NOTE]
   > I controlli ereditati devono essere in grado di essere `Protected` ancorati. Per modificare il livello di accesso di un controllo, impostarne la proprietà **Modifier** nella finestra **Proprietà** .

## <a name="see-also"></a>Vedi anche

- [Controlli di Windows Form](index.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura: agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cenni preliminari sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: agganciare i controlli in Windows Form](how-to-anchor-controls-on-windows-forms.md)
