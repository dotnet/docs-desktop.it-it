---
title: 'Procedura dettagliata: Specifica di voci di menu standard per un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964696"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Procedura dettagliata: Specifica di voci di menu standard per un modulo

È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.

Questa procedura dettagliata illustra come usare un <xref:System.Windows.Forms.MenuStrip> controllo per creare un menu standard. Il modulo risponde anche quando un utente seleziona una voce di menu. In questa procedura dettagliata vengono illustrate le attività seguenti:

- Creazione di un progetto Windows Forms.

- Creazione di un menu standard.

- Creazione di un <xref:System.Windows.Forms.StatusStrip> controllo.

- Gestione della selezione delle voci di menu.

Al termine, sarà presente un modulo con un menu standard che visualizza le selezioni delle voci di menu in un <xref:System.Windows.Forms.StatusStrip> controllo.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: specificare voci di menu standard in un modulo](how-to-provide-standard-menu-items-to-a-form.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione Windows denominato **StandardMenuForm** (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).

2. Nella Progettazione Windows Form selezionare il modulo.

## <a name="create-a-standard-menu"></a>Creare un menu standard

Il Progettazione Windows Form può popolare automaticamente un <xref:System.Windows.Forms.MenuStrip> controllo con le voci di menu standard.

1. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.MenuStrip> controllo nel form.

2. Fare clic sul <xref:System.Windows.Forms.MenuStrip> glifo azioni di progettazione del controllo ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) e selezionare **Inserisci elementi standard**.

     Il <xref:System.Windows.Forms.MenuStrip> controllo viene popolato con le voci di menu standard.

3. Fare clic sulla voce di menu **file** per visualizzare le voci di menu predefinite e le icone corrispondenti.

## <a name="create-a-statusstrip-control"></a>Creare un controllo StatusStrip

Usare il <xref:System.Windows.Forms.StatusStrip> controllo per visualizzare lo stato per le applicazioni Windows Forms. Nell'esempio corrente, le voci di menu selezionate dall'utente vengono visualizzate in un <xref:System.Windows.Forms.StatusStrip> controllo.

1. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.StatusStrip> controllo nel form.

     Il <xref:System.Windows.Forms.StatusStrip> controllo viene ancorato automaticamente alla fine del form.

2. Fare clic sul <xref:System.Windows.Forms.StatusStrip> pulsante a discesa del controllo e selezionare **StatusLabel** per aggiungere un <xref:System.Windows.Forms.ToolStripStatusLabel> controllo al <xref:System.Windows.Forms.StatusStrip> controllo.

## <a name="handle-item-selection"></a>Gestisci selezione elemento

Gestire l' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento per rispondere quando l'utente seleziona una voce di menu.

1. Fare clic sulla voce di menu **file** creata nella sezione Creazione di un menu standard.

2. Nella finestra **Proprietà** fare clic su **Eventi**.

3. Fare doppio clic sull' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.

     Il Progettazione Windows Form genera un gestore eventi per l' <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.

4. Inserire il codice seguente nel gestore eventi.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. Inserire la `UpdateStatus` definizione del metodo di utilità nel form.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>Checkpoint-testare il modulo

1. Premere **F5** per compilare ed eseguire il modulo.

2. Fare clic sulla voce di menu **file** per aprire il menu.

3. Nel menu **file** fare clic su uno degli elementi per selezionarlo.

     Il <xref:System.Windows.Forms.StatusStrip> controllo Visualizza l'elemento selezionato.

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata è stato creato un modulo con un menu standard. È possibile usare la <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molti altri scopi:

- Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip> . Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).

- Creare un form con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.ToolStrip> controlli di ancoraggio. Per altre informazioni, vedere [procedura dettagliata: creazione di un form MDI con Unione di menu e controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

- Assegnare ai <xref:System.Windows.Forms.ToolStrip> controlli un aspetto professionale. Per altre informazioni, vedere [procedura: impostare il renderer ToolStrip per un'applicazione](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
