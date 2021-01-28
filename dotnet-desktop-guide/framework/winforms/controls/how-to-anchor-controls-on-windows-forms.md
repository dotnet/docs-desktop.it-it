---
title: Ancorare i controlli (Anchor)
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: e7bc514f7347f257a6e2df67571c09df78f3c547
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957163"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Procedura: ancorare i controlli in Windows Form

Se si progetta un modulo che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono essere ridimensionati e riposizionati correttamente. Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form. La <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio per il controllo. Quando un controllo è ancorato a un form e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e le posizioni di ancoraggio. Se, ad esempio, si dispone di un <xref:System.Windows.Forms.TextBox> controllo ancorato ai bordi sinistro, destro e inferiore del form, quando il form viene ridimensionato, il <xref:System.Windows.Forms.TextBox> controllo viene ridimensionato orizzontalmente in modo da mantenere la stessa distanza dai lati destro e sinistro del form. Inoltre, il controllo si posiziona verticalmente in modo che la posizione sia sempre la stessa a distanza dal bordo inferiore del form. Se un controllo non è ancorato e il form viene ridimensionato, la posizione del controllo rispetto ai bordi del form viene modificata.

La <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Ancoraggio di un controllo in un form

1. In Visual Studio selezionare il controllo che si vuole ancorare.

    > [!NOTE]
    > È possibile ancorare più controlli simultaneamente premendo il tasto CTRL, facendo clic su ogni controllo per selezionarlo e quindi attenendosi al resto della procedura.

2. Nella finestra **Proprietà** fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Anchor%2A> Proprietà.

     Viene visualizzato un editor che mostra una croce.

3. Per impostare un ancoraggio, fare clic sulla sezione superiore, a sinistra, a destra o in basso della Croce.

     Per impostazione predefinita, i controlli sono ancorati nella parte superiore e sinistra.

4. Per cancellare un lato del controllo che è stato ancorato, fare clic su tale ARM della Croce.

5. Per chiudere l' <xref:System.Windows.Forms.Control.Anchor%2A> editor di proprietà, fare di nuovo clic sul <xref:System.Windows.Forms.Control.Anchor%2A> nome della proprietà.

Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato in modo che rimanga posizionato alla stessa distanza dal bordo del form. La distanza dal bordo ancorato rimane sempre uguale alla distanza definita quando il controllo è posizionato nell'Progettazione Windows Form.

> [!NOTE]
> Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> controllo, hanno un limite per l'altezza. L'ancoraggio del controllo nella parte inferiore del form o del contenitore non può forzare il superamento del limite di altezza del controllo.

I controlli ereditati devono essere in grado di essere `Protected` ancorati. Per modificare il livello di accesso di un controllo, impostarne la `Modifiers` proprietà nella finestra **Proprietà** .

## <a name="see-also"></a>Vedi anche

- [Controlli di Windows Form](index.md)
- [Cenni preliminari sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura: ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)
