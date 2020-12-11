---
title: 'Procedura dettagliata: Creazione di un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965896"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Procedura dettagliata: Creazione di un controllo ToolStrip professionale

È possibile assegnare ai controlli dell'applicazione <xref:System.Windows.Forms.ToolStrip> un aspetto e un comportamento professionali scrivendo una classe derivata dal <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.

In questa procedura dettagliata viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> i controlli per creare un controllo composito simile al **riquadro di spostamento** fornito da Microsoft® Outlook®. In questa procedura dettagliata vengono illustrate le attività seguenti:

- Creazione di un progetto libreria di controlli Windows.

- Progettazione del controllo StackView.

- Implementazione di un renderer personalizzato.

Al termine, si disporrà di un controllo client personalizzato riutilizzabile con l'aspetto professionale di un controllo Microsoft Office® XP.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: creare un controllo ToolStrip professionalmente](how-to-create-a-professionally-styled-toolstrip-control.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-control-library-project"></a>Creare il progetto di libreria di controlli

1. In Visual Studio creare un nuovo progetto di libreria di controlli Windows denominato `StackViewLibrary` .

2. In **Esplora soluzioni** eliminare il controllo predefinito del progetto eliminando il file di origine denominato "UserControl1.cs" o "UserControl1. vb", a seconda del linguaggio scelto.

     Per altre informazioni, vedere [procedura: rimuovere, eliminare ed escludere elementi](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).

3. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento al progetto **StackViewLibrary** . Assegnare al nuovo file di origine il nome di base `StackView` .

## <a name="design-the-stackview-control"></a>Progettare il controllo StackView

Il `StackView` controllo è un controllo composito con un <xref:System.Windows.Forms.ToolStrip> controllo figlio. Per altre informazioni sui controlli compositi, vedere [varietà di controlli personalizzati](varieties-of-custom-controls.md).

1. Dalla **casella degli strumenti** trascinare un <xref:System.Windows.Forms.ToolStrip> controllo nell'area di progettazione.

2. Nella finestra **Proprietà** impostare le proprietà del <xref:System.Windows.Forms.ToolStrip> controllo in base alla tabella seguente.

    |Proprietà|Valore|
    |--------------|-----------|
    |Nome|`stackStrip`|
    |CanOverflow|`false`|
    |Dock|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |Carattere|`Tahoma, 10pt, style=Bold`|
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |Riempimento|`0, 7, 0, 0`|
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. Nella Progettazione Windows Form fare clic sul <xref:System.Windows.Forms.ToolStrip> pulsante **Aggiungi** del controllo e aggiungere un oggetto <xref:System.Windows.Forms.ToolStripButton> al `stackStrip` controllo.

4. Nella finestra **Proprietà** impostare le proprietà del <xref:System.Windows.Forms.ToolStripButton> controllo in base alla tabella seguente.

    |Proprietà|Valore|
    |--------------|-----------|
    |Nome|`mailStackButton`|
    |CheckOnClick|true|
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |ImageTransparentColor|`238, 238, 238`|
    |Margin|`0, 0, 0, 0`|
    |Riempimento|`3, 3, 3, 3`|
    |Testo|**Posta elettronica**|
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. Ripetere il passaggio 7 per altri tre <xref:System.Windows.Forms.ToolStripButton> controlli.

     Denominare i controlli `calendarStackButton` , `contactsStackButton` e `tasksStackButton` . Impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà su **Calendar**, **Contacts** e **Tasks** rispettivamente.

## <a name="handle-events"></a>Gestire eventi

Due eventi sono importanti per fare in `StackView` modo che il controllo si comporti correttamente. Gestire l' <xref:System.Windows.Forms.UserControl.Load> evento per posizionare correttamente il controllo. Gestire l' <xref:System.Windows.Forms.ToolStripItem.Click> evento per ogni oggetto <xref:System.Windows.Forms.ToolStripButton> per fornire il `StackView` comportamento dello stato del controllo simile al <xref:System.Windows.Forms.RadioButton> controllo.

1. Nella Progettazione Windows Form selezionare il `StackView` controllo.

2. Nella finestra **Proprietà** fare clic su **Eventi**.

3. Fare doppio clic sull'evento Load per generare il `StackView_Load` gestore eventi.

4. Nel gestore di eventi `StackView_Load` copiare e incollare il codice riportato di seguito.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. Nella Progettazione Windows Form selezionare il `mailStackButton` controllo.

6. Nella finestra **Proprietà** fare clic su **Eventi**.

7. Fare doppio clic sull'evento click.

     Il Progettazione Windows Form genera il `mailStackButton_Click` gestore eventi.

8. Rinominare il `mailStackButton_Click` gestore eventi in `stackButton_Click` .

     Per altre informazioni, vedere [rinominare un simbolo di codice refactoring](/visualstudio/ide/reference/rename).

9. Inserire il codice seguente nel `stackButton_Click` gestore eventi.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. Nella Progettazione Windows Form selezionare il `calendarStackButton` controllo.

11. Nella finestra **Proprietà** impostare l'evento click sul `stackButton_Click` gestore eventi.

12. Ripetere i passaggi 10 e 11 per `contactsStackButton` i `tasksStackButton` controlli e.

## <a name="define-icons"></a>Definisci icone

A ogni `StackView` pulsante è associata un'icona. Per praticità, ogni icona viene rappresentata come stringa con codifica Base64, che viene deserializzata prima <xref:System.Drawing.Bitmap> della creazione di un oggetto. In un ambiente di produzione i dati bitmap vengono archiviati come risorsa e le icone vengono visualizzate nel Progettazione Windows Form. Per altre informazioni, vedere [procedura: aggiungere immagini di sfondo a Windows Forms](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).

1. Nell'editor di codice inserire il codice seguente nella definizione della `StackView` classe. Questo codice inizializza le bitmap per le <xref:System.Windows.Forms.ToolStripButton> icone.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. Aggiungere una chiamata al `InitializeImages` metodo nel costruttore della `StackView` classe.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a>Implementare un renderer personalizzato

È possibile personalizzare la maggior parte degli elementi del `StackView` controllo implementando una classe che deriva dalla <xref:System.Windows.Forms.ToolStripRenderer> classe. In questa procedura verrà implementata una <xref:System.Windows.Forms.ToolStripProfessionalRenderer> classe che Personalizza il grip e disegna sfondi sfumatura per i <xref:System.Windows.Forms.ToolStripButton> controlli.

1. Inserire il codice seguente nella `StackView` definizione del controllo.

     Si tratta della definizione della `StackRenderer` classe, che esegue l'override <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> dei <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> metodi, e <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> per produrre un aspetto personalizzato.

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. Nel `StackView` costruttore del controllo creare una nuova istanza della `StackRenderer` classe e assegnare questa istanza alla `stackStrip` proprietà del controllo <xref:System.Windows.Forms.ToolStrip.Renderer%2A> .

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a>Testare il controllo StackView

Il `StackView` controllo deriva dalla <xref:System.Windows.Forms.UserControl> classe. Pertanto, è possibile testare il controllo con il **contenitore di test UserControl**. Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

1. Premere **F5** per compilare il progetto e avviare **UserControl Test Container**.

2. Spostare il puntatore sui pulsanti del `StackView` controllo, quindi fare clic su un pulsante per visualizzare l'aspetto dello stato selezionato.

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata è stato creato un controllo client personalizzato riutilizzabile con l'aspetto professionale di un controllo di Office XP. È possibile usare la <xref:System.Windows.Forms.ToolStrip> famiglia di controlli per molti altri scopi:

- Creare menu di scelta rapida per i controlli con <xref:System.Windows.Forms.ContextMenuStrip> . Per altre informazioni, vedere [Cenni preliminari sui componenti ContextMenu](contextmenu-component-overview-windows-forms.md).

- Creare un modulo con un menu standard popolato automaticamente. Per ulteriori informazioni, vedere [procedura dettagliata: fornire voci di menu standard a un modulo](walkthrough-providing-standard-menu-items-to-a-form.md).

- Creare un form con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.ToolStrip> controlli di ancoraggio. Per altre informazioni, vedere [procedura: creare un form MDI con Unione di menu e controlli ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
- [Procedura: Specificare voci di menu standard per un modulo](how-to-provide-standard-menu-items-to-a-form.md)
