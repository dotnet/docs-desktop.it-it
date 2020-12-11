---
title: 'Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c619900ea0b7f1b50976fec8d26dd3145dc07693
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965158"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedura: testare il comportamento della fase di esecuzione di UserControl

Quando si sviluppa un <xref:System.Windows.Forms.UserControl> , è necessario testarne il comportamento in fase di esecuzione. È possibile creare un progetto di applicazione basato su Windows separato e inserire il controllo in un form di test, ma questa procedura non è praticabile. Un modo più rapido e semplice consiste nell'usare il **contenitore di test UserControl** fornito da Visual Studio. Questo contenitore di test viene avviato direttamente dal progetto libreria di controlli Windows.

> [!IMPORTANT]
> Per il caricamento del contenitore di test <xref:System.Windows.Forms.UserControl> , il controllo deve avere almeno un costruttore pubblico.
> [!NOTE]
> Non è possibile testare un controllo Visual C++ usando il **contenitore di test UserControl**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Testare il comportamento in fase di esecuzione di un UserControl

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer**.

2. Nella **Progettazione Windows Form** trascinare un <xref:System.Windows.Forms.Label> controllo dalla **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il **contenitore di test UserControl**. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .

4. Selezionare la <xref:System.Windows.Forms.Control.BackColor%2A> Proprietà visualizzata nel <xref:System.Windows.Forms.PropertyGrid> controllo a destra del riquadro di **Anteprima** . Modificare il valore in **ControlDark**. Osservare che il controllo viene modificato in un colore più scuro. Provare a modificare altri valori di proprietà e osservare l'effetto sul controllo.

5. Fare clic sulla casella di **controllo Dock Fill User Control** sotto il riquadro di **Anteprima** . Si noti che il controllo viene ridimensionato per riempire il riquadro. Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.

6. Chiudere il contenitore di test.

7. Aggiungere un altro controllo utente al progetto **EsempioTestContainer** .

8. Nella **Progettazione Windows Form** trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nell'area di progettazione del controllo.

9. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test.

10. Fare clic sul **controllo Seleziona utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente.

## <a name="test-user-controls-from-another-project"></a>Testare i controlli utente da un altro progetto

È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer2**.

2. Nella **Progettazione Windows Form** trascinare un <xref:System.Windows.Forms.RadioButton> controllo dalla **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .

4. Fare clic sul pulsante **Carica** .

5. Nella finestra di dialogo **Apri** passare alla *TestContainerExample.dll*, compilata nella procedura precedente. Selezionare *TestContainerExample.dll* e fare clic sul pulsante **Apri** per caricare i controlli utente.

6. Usare il **controllo Seleziona utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal progetto **EsempioTestContainer** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Procedura: Creare controlli compositi](how-to-author-composite-controls.md)
- [Procedura dettagliata: modifica di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Progettazione controllo utente](/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
