---
title: Layout dei controlli con spaziatura interna, margini e proprietà AutoSize
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: 84b1a5d20d273bb9dee6e7f97cf8bd569e5e97ab
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957578"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Procedura dettagliata: disposizione dei controlli con spaziatura interna, margini e proprietà AutoSize

Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form. Il **Progettazione Windows Form** in Visual Studio offre molti strumenti di layout a questo scopo. Tre dei più importanti sono le <xref:System.Windows.Forms.Control.Margin%2A> proprietà, <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.AutoSize%2A> , che sono presenti in tutti i controlli Windows Form.

La proprietà <xref:System.Windows.Forms.Control.Margin%2A> definisce lo spazio intorno al controllo per mantenere gli altri controlli a una specifica distanza dai bordi del controllo stesso.

La proprietà <xref:System.Windows.Forms.Control.Padding%2A> definisce lo spazio all'interno di un controllo per mantenere il contenuto del controllo, ad esempio il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A>, a una specifica distanza dai bordi del controllo stesso.

L'illustrazione seguente mostra le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> in un controllo.

![Spaziatura e margine per controlli Windows Form](./media/vs-winformpadmargin.gif)

La <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà indica a un controllo di ridimensionarsi automaticamente in base al relativo contenuto. Non verrà ridimensionato in modo da essere minore del valore della proprietà originale <xref:System.Windows.Forms.Control.Size%2A> e verrà considerato il valore della relativa <xref:System.Windows.Forms.Control.Padding%2A> Proprietà.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di **applicazione Windows** denominato `LayoutExample` .

2. Selezionare il modulo nella **Progettazione Windows Form**.

## <a name="set-margins-for-controls"></a>Impostare i margini per i controlli

È possibile impostare la distanza predefinita tra i controlli usando la <xref:System.Windows.Forms.Control.Margin%2A> Proprietà. Quando si sposta un controllo abbastanza vicino a un altro controllo, viene visualizzata una guide di allineamento che mostra i margini dei due controlli. Il controllo che si sta spostando verrà inoltre bloccato sulla distanza definita dai margini.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Disporre i controlli nel form usando la proprietà Margin

1. Trascinare due <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form.

2. Selezionare uno dei <xref:System.Windows.Forms.Button> controlli e spostarlo vicino all'altro, fino a quando non sono quasi in contatto.

   Osservare la guide di allineamento visualizzata tra di essi. Questa distanza è la somma dei valori dei due controlli <xref:System.Windows.Forms.Control.Margin%2A> . Il controllo spostato si blocca a questa distanza. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli su Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

3. Modificare la <xref:System.Windows.Forms.Control.Margin%2A> proprietà di uno dei controlli espandendo la <xref:System.Windows.Forms.Control.Margin%2A> voce nella finestra **proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su **20**.

4. Selezionare uno dei <xref:System.Windows.Forms.Button> controlli e spostarlo vicino all'altro.

   La pagina di allineamento che definisce la somma dei valori dei margini è più lunga e il controllo si blocca a una distanza maggiore rispetto all'altro.

5. Modificare la <xref:System.Windows.Forms.Control.Margin%2A> proprietà del controllo selezionato espandendo la <xref:System.Windows.Forms.Control.Margin%2A> voce nella finestra **proprietà** e impostando la <xref:System.Windows.Forms.Padding.Top%2A> proprietà su **5**.

6. Spostare il controllo selezionato sotto l'altro controllo e osservare che la guide di allineamento è più breve. Spostare il controllo selezionato a sinistra dell'altro controllo e osservare che la Guida di allineamento mantiene il valore osservato nel passaggio 4.

7. È possibile impostare tutti gli aspetti della <xref:System.Windows.Forms.Control.Margin%2A> proprietà,,, <xref:System.Windows.Forms.Padding.Left%2A> , <xref:System.Windows.Forms.Padding.Top%2A> <xref:System.Windows.Forms.Padding.Right%2A> <xref:System.Windows.Forms.Padding.Bottom%2A> su valori diversi oppure è possibile impostarli tutti sullo stesso valore con la <xref:System.Windows.Forms.Padding.All%2A> Proprietà.

## <a name="set-padding-for-controls"></a>Imposta spaziatura interna per i controlli

Per ottenere il layout preciso necessario per l'applicazione, i controlli contengono spesso controlli figlio. Quando si desidera specificare la prossimità del bordo del controllo figlio al bordo del controllo padre, utilizzare la proprietà del controllo padre insieme alla <xref:System.Windows.Forms.Control.Padding%2A> proprietà del controllo figlio <xref:System.Windows.Forms.Control.Margin%2A> . La <xref:System.Windows.Forms.Control.Padding%2A> proprietà viene inoltre utilizzata per controllare la prossimità del contenuto di un controllo (ad esempio, la <xref:System.Windows.Forms.Button> proprietà di un controllo <xref:System.Windows.Forms.Control.Text%2A> ) ai bordi.

### <a name="arrange-controls-on-your-form-using-padding"></a>Disporre i controlli nel form usando la spaziatura interna

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Modificare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> in **true**.

3. Modificare la <xref:System.Windows.Forms.Control.Padding%2A> Proprietà espandendo la <xref:System.Windows.Forms.Control.Padding%2A> voce nella finestra **proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su **5**.

   Il controllo si espande per fornire spazio per la nuova spaziatura interna.

4. Trascinare un controllo <xref:System.Windows.Forms.GroupBox> dalla **Casella degli strumenti** al form. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nel <xref:System.Windows.Forms.GroupBox> controllo. Posizionare il <xref:System.Windows.Forms.Button> controllo in modo che sia allineato all'angolo inferiore destro del <xref:System.Windows.Forms.GroupBox> controllo.

   Osservare le guide di allineamento visualizzate quando il <xref:System.Windows.Forms.Button> controllo si avvicina ai bordi inferiore e destro del <xref:System.Windows.Forms.GroupBox> controllo. Queste guide di allineamento corrispondono alla <xref:System.Windows.Forms.Control.Margin%2A> proprietà di <xref:System.Windows.Forms.Button> .

5. Modificare la <xref:System.Windows.Forms.GroupBox> proprietà del controllo <xref:System.Windows.Forms.Control.Padding%2A> espandendo la <xref:System.Windows.Forms.Control.Padding%2A> voce nella finestra **Proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su **20**.

6. Selezionare il <xref:System.Windows.Forms.Button> controllo all'interno del <xref:System.Windows.Forms.GroupBox> controllo e spostarlo verso il centro del <xref:System.Windows.Forms.GroupBox> .

   Le guide di allineamento vengono visualizzate a una distanza maggiore dai bordi del <xref:System.Windows.Forms.GroupBox> controllo. Questa distanza è la somma della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Margin%2A> e della <xref:System.Windows.Forms.GroupBox> proprietà del controllo <xref:System.Windows.Forms.Control.Padding%2A> .

## <a name="size-controls-automatically"></a>Ridimensiona automaticamente i controlli

In alcune applicazioni, le dimensioni di un controllo non saranno uguali in fase di esecuzione, come in fase di progettazione. Il testo di un <xref:System.Windows.Forms.Button> controllo, ad esempio, può essere tratto da un database e la sua lunghezza non è nota in anticipo.

Quando la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà è impostata su `true` , il controllo verrà ridimensionato in base al relativo contenuto. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Disporre i controlli nel form usando la proprietà AutoSize

1. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.

2. Modificare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> in **true**.

3. Modificare la <xref:System.Windows.Forms.Button> proprietà del controllo impostando <xref:System.Windows.Forms.Control.Text%2A> **questo pulsante su un valore String lungo per la proprietà Text**.

   Quando si esegue il commit della modifica, il <xref:System.Windows.Forms.Button> controllo viene ridimensionato per adattarsi al nuovo testo.

4. Trascinare un altro <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nel form.

5. Modificare la <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Text%2A> in "**questo pulsante ha una stringa lungo per la relativa proprietà Text".**

   Quando si esegue il commit della modifica, il <xref:System.Windows.Forms.Button> controllo non viene ridimensionato automaticamente e il testo viene ritagliato in base al bordo destro del controllo.

6. Modificare la <xref:System.Windows.Forms.Control.Padding%2A> Proprietà espandendo la <xref:System.Windows.Forms.Control.Padding%2A> voce nella finestra **proprietà** e impostando la <xref:System.Windows.Forms.Padding.All%2A> proprietà su **5**.

   Il testo nell'interno del controllo viene ritagliato su tutti e quattro i lati.

7. Modificare la <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> in **true**.

   Il <xref:System.Windows.Forms.Button> controllo viene ridimensionato per includere l'intera stringa. È stata inoltre aggiunta la spaziatura interna intorno al testo, <xref:System.Windows.Forms.Button> che determina l'espansione del controllo in tutte e quattro le direzioni.

8. Trascinare un controllo <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form. Posizionarlo vicino all'angolo inferiore destro del form.

9. Modificare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> in **true**.

10. Impostare la <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su <xref:System.Windows.Forms.AnchorStyles.Right> <xref:System.Windows.Forms.AnchorStyles.Bottom> .

11. Modificare la <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Text%2A> in "**questo pulsante ha una stringa lungo per la relativa proprietà Text".**

   Quando si esegue il commit della modifica, il <xref:System.Windows.Forms.Button> controllo si ridimensiona verso sinistra. In generale, il ridimensionamento automatico aumenterà le dimensioni di un controllo nella direzione opposta all' <xref:System.Windows.Forms.Control.Anchor%2A> impostazione della proprietà.

## <a name="autosize-and-autosizemode-properties"></a>Proprietà AutoSize e AutoSizeMode

 Alcuni controlli supportano la `AutoSizeMode` proprietà, che offre un controllo più granulare sul comportamento di ridimensionamento automatico di un controllo.

### <a name="use-the-autosizemode-property"></a>Usare la proprietà AutoSizeMode

1. Trascinare un controllo <xref:System.Windows.Forms.Panel> dalla **Casella degli strumenti** al form.

2. Impostare il valore della <xref:System.Windows.Forms.Panel> proprietà del controllo <xref:System.Windows.Forms.Control.AutoSize%2A> su **true**.

3. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nel <xref:System.Windows.Forms.Panel> controllo.

4. Posizionare il <xref:System.Windows.Forms.Button> controllo vicino all'angolo inferiore destro del <xref:System.Windows.Forms.Panel> controllo.

5. Selezionare il <xref:System.Windows.Forms.Panel> controllo e il quadratino di ridimensionamento in basso a destra. Ridimensionare il <xref:System.Windows.Forms.Panel> controllo in modo che sia maggiore e minore.

   > [!NOTE]
   > È possibile ridimensionare liberamente il <xref:System.Windows.Forms.Panel> controllo, ma non è possibile ridimensionarlo più in basso rispetto alla posizione dell' <xref:System.Windows.Forms.Button> angolo inferiore destro del controllo. Questo comportamento viene specificato dal valore predefinito della `AutoSizeMode` proprietà, ovvero <xref:System.Windows.Forms.AutoSizeMode.GrowOnly> .

6. Impostare il valore della <xref:System.Windows.Forms.Panel> proprietà del controllo `AutoSizeMode` su <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink> .

   Il <xref:System.Windows.Forms.Panel> controllo viene ridimensionato per racchiudere il <xref:System.Windows.Forms.Button> controllo. Non è possibile ridimensionare il <xref:System.Windows.Forms.Panel> controllo.

7. Trascinare il <xref:System.Windows.Forms.Button> controllo verso l'angolo superiore sinistro del <xref:System.Windows.Forms.Panel> controllo.

   Il <xref:System.Windows.Forms.Panel> controllo viene ridimensionato alla <xref:System.Windows.Forms.Button> nuova posizione del controllo.

## <a name="next-steps"></a>Passaggi successivi

Sono disponibili molte altre funzionalità di layout per la disposizione dei controlli nelle applicazioni Windows Form. Di seguito sono riportate alcune combinazioni che è possibile provare:

- Compilare un form usando un <xref:System.Windows.Forms.TableLayoutPanel> controllo. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Provare a modificare i valori della <xref:System.Windows.Forms.TableLayoutPanel> proprietà del controllo <xref:System.Windows.Forms.Control.Padding%2A> , nonché la <xref:System.Windows.Forms.Control.Margin%2A> proprietà sui relativi controlli figlio.

- Provare lo stesso esperimento usando un <xref:System.Windows.Forms.FlowLayoutPanel> controllo. Per informazioni dettagliate, vedere [procedura dettagliata: disposizione dei controlli in Windows Form tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

- Sperimentare l'ancoraggio dei controlli figlio in un <xref:System.Windows.Forms.Panel> controllo. La <xref:System.Windows.Forms.Control.Padding%2A> proprietà è una realizzazione più generale della <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> proprietà ed è possibile soddisfarla in questo caso inserendo un controllo figlio in un <xref:System.Windows.Forms.Panel> controllo e impostando la proprietà del controllo figlio <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill> . Impostare la <xref:System.Windows.Forms.Panel> proprietà del controllo <xref:System.Windows.Forms.Control.Padding%2A> su vari valori e annotare l'effetto.

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Cenni preliminari sulla proprietà AutoSize](autosize-property-overview.md)
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
