---
title: 'Procedura dettagliata: Creazione di un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: d71534bed0af142ff71ba9a0c01207b2c72a6d6a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965893"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Procedura dettagliata: Creazione di un modulo con interfaccia a documenti multipli con unione di menu e controlli ToolStrip

Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu. I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.

In questa procedura dettagliata viene illustrato come utilizzare i <xref:System.Windows.Forms.ToolStripPanel> controlli con un form MDI. Il form supporta anche l'unione dei menu con menu figlio. In questa procedura dettagliata vengono illustrate le attività seguenti:

- Creazione di un progetto Windows Forms.

- Creazione del menu principale per il form. Il nome effettivo del menu varierà.

- Aggiunta del <xref:System.Windows.Forms.ToolStripPanel> controllo alla **casella degli strumenti**.

- Creazione di un form figlio.

- Disposizione <xref:System.Windows.Forms.ToolStripPanel> dei controlli in base all'ordine z.

Al termine, sarà presente un form MDI che supporta l'Unione di menu e i <xref:System.Windows.Forms.ToolStrip> controlli mobili.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un form MDI con Unione di menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione Windows denominato **MDIForm** (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).

2. Nella Progettazione Windows Form selezionare il modulo.

3. Nella Finestra Proprietà impostare il valore di <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true` .

## <a name="create-the-main-menu"></a>Creare il menu principale

Il form padre MDI contiene il menu principale. Nel menu principale è presente una voce di menu denominata **Window**. Con la voce di menu **finestra** è possibile creare form figlio. Le voci di menu dei form figlio vengono unite nel menu principale.

1. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.

2. Aggiungere un oggetto <xref:System.Windows.Forms.ToolStripMenuItem> al <xref:System.Windows.Forms.MenuStrip> controllo e denominarlo **Window**.

3. Selezionare il controllo <xref:System.Windows.Forms.MenuStrip>.

4. Nella Finestra Proprietà impostare il valore della <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà su `ToolStripMenuItem1` .

5. Aggiungere un elemento secondario alla voce di menu **finestra** , quindi denominare il **nuovo** elemento secondario.

6. Nella finestra Proprietà fare clic su **Eventi**.

7. Fare doppio clic sull' <xref:System.Windows.Forms.ToolStripItem.Click> evento.

     Il Progettazione Windows Form genera un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento.

8. Inserire il codice seguente nel gestore eventi.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Aggiungere il controllo ToolStripPanel alla casella degli strumenti

Quando si usano <xref:System.Windows.Forms.MenuStrip> i controlli con un form MDI, è necessario avere il <xref:System.Windows.Forms.ToolStripPanel> controllo. È necessario aggiungere il <xref:System.Windows.Forms.ToolStripPanel> controllo alla **casella degli strumenti** per compilare il form MDI nell'progettazione Windows Form.

1. Aprire la **casella degli strumenti**, quindi fare clic sulla scheda **tutti Windows Forms** per visualizzare i controlli Windows Forms disponibili.

2. Fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida e **scegliere Scegli elementi**.

3. Nella finestra di dialogo **Scegli elementi della casella degli strumenti** scorrere verso il basso la colonna **nome** fino a quando non si trova **ToolStripPanel**.

4. Selezionare la casella di controllo in base a **ToolStripPanel**, quindi fare clic su **OK**.

     Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene visualizzato nella **casella degli strumenti**.

## <a name="create-a-child-form"></a>Creare un form figlio

In questa procedura verrà definita una classe di form figlio separata che dispone di un proprio <xref:System.Windows.Forms.MenuStrip> controllo. Le voci di menu per questo form sono unite a quelle del form padre.

1. Aggiungere un nuovo form denominato `ChildForm` al progetto.

     Per altre informazioni, vedere [procedura: aggiungere Windows Forms a un progetto](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form figlio.

3. Fare clic sul <xref:System.Windows.Forms.MenuStrip> glifo azioni di progettazione del controllo ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ), quindi selezionare **modifica elementi**.

4. Nella finestra di dialogo **Editor raccolta elementi** aggiungere un nuovo <xref:System.Windows.Forms.ToolStripMenuItem> denominato **ChildMenuItem** al menu figlio.

     Per altre informazioni, vedere [ToolStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).

## <a name="test-the-form"></a>Testare il modulo

1. Premere **F5** per compilare ed eseguire il modulo.

2. Fare clic sulla voce di menu **finestra** per aprire il menu, quindi fare clic su **nuovo**.

     Un nuovo form figlio viene creato nell'area client MDI del form. Il menu del form figlio viene unito al menu principale.

3. Chiudere il form figlio.

     Il menu del form figlio viene rimosso dal menu principale.

4. Fare clic su **nuovo** più volte.

     I form figlio vengono elencati automaticamente sotto la voce di menu **finestra** perché la <xref:System.Windows.Forms.MenuStrip> proprietà del controllo <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> è assegnata.

## <a name="add-toolstrip-support"></a>Aggiungi supporto ToolStrip

In questa procedura vengono aggiunti quattro <xref:System.Windows.Forms.ToolStrip> controlli al form padre MDI. Ogni <xref:System.Windows.Forms.ToolStrip> controllo viene aggiunto all'interno di un <xref:System.Windows.Forms.ToolStripPanel> controllo, che è ancorato al bordo del form.

1. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.ToolStripPanel> controllo nel form.

2. Con il <xref:System.Windows.Forms.ToolStripPanel> controllo selezionato, fare doppio clic sul <xref:System.Windows.Forms.ToolStrip> controllo nella **casella degli strumenti**.

     <xref:System.Windows.Forms.ToolStrip>Viene creato un controllo nel <xref:System.Windows.Forms.ToolStripPanel> controllo.

3. Selezionare il controllo <xref:System.Windows.Forms.ToolStripPanel>.

4. Nella Finestra Proprietà modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Control.Dock%2A> in <xref:System.Windows.Forms.DockStyle.Left> .

     Il <xref:System.Windows.Forms.ToolStripPanel> controllo viene ancorato al lato sinistro del form, sotto il menu principale. L'area client MDI viene ridimensionata per adattarsi al <xref:System.Windows.Forms.ToolStripPanel> controllo.

5. Ripetere i passaggi da 1 a 4.

     Ancorare il nuovo <xref:System.Windows.Forms.ToolStripPanel> controllo alla parte superiore del form.

     Il <xref:System.Windows.Forms.ToolStripPanel> controllo è ancorato al di sotto del menu principale, ma a destra del primo <xref:System.Windows.Forms.ToolStripPanel> controllo. Questo passaggio illustra l'importanza dell'ordine z nel posizionamento corretto dei <xref:System.Windows.Forms.ToolStripPanel> controlli.

6. Ripetere i passaggi da 1 a 4 per altri due <xref:System.Windows.Forms.ToolStripPanel> controlli.

     Ancorare i nuovi <xref:System.Windows.Forms.ToolStripPanel> controlli a destra e in basso nel form.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>Disporre i controlli ToolStripPanel in base all'ordine Z

La posizione di un controllo ancorato <xref:System.Windows.Forms.ToolStripPanel> nel form MDI è determinata dalla posizione del controllo nell'ordine z. È possibile organizzare facilmente l'ordine z dei controlli nella finestra Struttura documento.

1. Scegliere **altre finestre** dal menu **Visualizza** , quindi fare clic su **struttura documento**.

     La disposizione dei <xref:System.Windows.Forms.ToolStripPanel> controlli dalla procedura precedente non è standard. Questo è dovuto al fatto che l'ordine z non è corretto. Utilizzare la finestra Struttura documento per modificare l'ordine z dei controlli.

2. Nella finestra Struttura documento selezionare **ToolStripPanel4**.

3. Fare clic ripetutamente sul pulsante freccia giù, fino a quando **ToolStripPanel4** non si trova nella parte inferiore dell'elenco.

     Il controllo **ToolStripPanel4** è ancorato alla parte inferiore del form, sotto gli altri controlli.

4. Selezionare **ToolStripPanel2**.

5. Fare clic sul pulsante freccia giù una volta per posizionare il terzo controllo nell'elenco.

     Il controllo **ToolStripPanel2** è ancorato alla parte superiore del form, sotto il menu principale e sopra gli altri controlli.

6. Selezionare vari controlli nella finestra **struttura documento** e spostarli in posizioni diverse nell'ordine z. Si noti l'effetto dell'ordine z sul posizionamento dei controlli ancorati. Usare CTRL + Z o **Annulla** nel menu **modifica** per annullare le modifiche.

## <a name="checkpoint---test-your-form"></a>Checkpoint-testare il modulo

1. Premere **F5** per compilare ed eseguire il modulo.

2. Fare clic sul riquadro di <xref:System.Windows.Forms.ToolStrip> controllo e trascinare il controllo in posizioni diverse sul form.

     È possibile trascinare un <xref:System.Windows.Forms.ToolStrip> controllo da un <xref:System.Windows.Forms.ToolStripPanel> controllo a un altro.

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata è stato creato un form padre MDI con <xref:System.Windows.Forms.ToolStrip> controlli e Unione di menu. È possibile usare la <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molti altri scopi:

- Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip> . Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).

- Creazione di un form con un menu standard popolato automaticamente. Per ulteriori informazioni, vedere [procedura dettagliata: fornire voci di menu standard a un modulo](walkthrough-providing-standard-menu-items-to-a-form.md).

- Assegnare ai <xref:System.Windows.Forms.ToolStrip> controlli un aspetto professionale. Per altre informazioni, vedere [procedura: impostare il renderer ToolStrip per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Procedura: Creare form padre MDI](../advanced/how-to-create-mdi-parent-forms.md)
- [Procedura: Creare form figlio MDI](../advanced/how-to-create-mdi-child-forms.md)
- [Procedura: Inserire un elemento MenuStrip in un menu a discesa di interfaccia a documenti multipli](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
