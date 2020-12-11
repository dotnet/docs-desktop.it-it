---
title: "Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961918"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.

<xref:System.Windows.Forms.ToolBar> i pulsanti sono in grado di visualizzare le icone al loro interno per facilitarne l'identificazione da parte degli utenti. Questa operazione viene eseguita tramite l'aggiunta di immagini al <xref:System.Windows.Forms.ImageList> componente e l'associazione con il <xref:System.Windows.Forms.ToolBar> controllo.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.ToolBar> controllo e un <xref:System.Windows.Forms.ImageList> componente. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione

1. Aggiungere immagini al <xref:System.Windows.Forms.ImageList> componente. Per altre informazioni, vedere [procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione](how-to-add-or-remove-imagelist-images-with-the-designer.md).

2. Selezionare il <xref:System.Windows.Forms.ToolBar> controllo nel form.

3. Nella finestra **Proprietà** impostare la proprietà del <xref:System.Windows.Forms.ToolBar> controllo sul <xref:System.Windows.Forms.ToolBar.ImageList%2A> <xref:System.Windows.Forms.ImageList> componente.

4. Fare clic sulla <xref:System.Windows.Forms.ToolBar> proprietà del controllo <xref:System.Windows.Forms.ToolBar.Buttons%2A> per selezionarla, quindi fare clic sui puntini di sospensione ( ![ ...) nel pulsante finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) per aprire l' **Editor della raccolta ToolBarButton**.

5. Usare il pulsante **Aggiungi** per aggiungere pulsanti al <xref:System.Windows.Forms.ToolBar> controllo.

6. Nella finestra **Proprietà** visualizzata nel riquadro sul lato destro dell' **Editor della raccolta ToolBarButton**, impostare la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà di ogni pulsante della barra degli strumenti su uno dei valori dell'elenco, che viene disegnato dalle immagini aggiunte al <xref:System.Windows.Forms.ImageList> componente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
