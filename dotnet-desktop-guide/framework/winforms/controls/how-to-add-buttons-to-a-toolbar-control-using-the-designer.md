---
title: 'Procedura: Aggiungere pulsanti a un controllo ToolBar usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962113"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Procedura: Aggiungere pulsanti a un controllo ToolBar usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.

Una parte integrante del <xref:System.Windows.Forms.ToolBar> controllo è costituita dai pulsanti da aggiungere. Questi possono essere usati per semplificare l'accesso ai comandi di menu o, in alternativa, possono essere posizionati in un'altra area dell'interfaccia utente dell'applicazione per esporre i comandi agli utenti che non sono disponibili nella struttura dei menu.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.ToolBar> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-buttons-at-design-time"></a>Per aggiungere pulsanti in fase di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.ToolBar>.

2. Nella finestra **Proprietà** fare clic sulla <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarla e fare clic sui **puntini** di sospensione ( ![ il pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) per aprire l' **Editor della raccolta ToolBarButton**.

3. Usare i pulsanti **Aggiungi** e **Rimuovi** per aggiungere e rimuovere i pulsanti dal <xref:System.Windows.Forms.ToolBar> controllo.

4. Configurare le proprietà dei singoli pulsanti nella finestra **Proprietà** visualizzata nel riquadro sul lato destro dell'editor. Nella tabella seguente vengono illustrate alcune proprietà importanti da considerare.

    |Proprietà|Descrizione|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Imposta il menu da visualizzare nel pulsante della barra degli strumenti a discesa. La proprietà del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton> . Questa proprietà accetta un'istanza della <xref:System.Windows.Forms.ContextMenu> classe come riferimento.|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Imposta un valore che indica se un pulsante della barra degli strumenti di tipo interruttore viene inserito parzialmente. La proprietà del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> .|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Imposta un valore che indica se un pulsante della barra degli strumenti di tipo interruttore si trova attualmente nello stato di push. La proprietà del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> o <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton> .|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Imposta lo stile del pulsante della barra degli strumenti. Deve essere uno dei valori dell' <xref:System.Windows.Forms.ToolBarButtonStyle> enumerazione.|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Stringa di testo visualizzata dal pulsante.|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Testo visualizzato come descrizione comando per il pulsante.|

5. Fare clic su **OK** per chiudere la finestra di dialogo e creare i pannelli specificati.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)
- [Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Panoramica del controllo ToolBar](toolbar-control-overview-windows-forms.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
