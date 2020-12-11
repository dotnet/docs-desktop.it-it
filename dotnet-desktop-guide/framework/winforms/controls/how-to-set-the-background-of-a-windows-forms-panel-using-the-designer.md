---
title: Impostare lo sfondo di un pannello utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965221"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Procedura: impostare lo sfondo di un pannello di Windows Forms utilizzando la finestra di progettazione

Un <xref:System.Windows.Forms.Panel> controllo Windows Forms può visualizzare sia un colore di sfondo che un'immagine di sfondo. La <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti nel pannello, ad esempio etichette e pulsanti di opzione. Se la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà non è impostata, la <xref:System.Windows.Forms.Control.BackColor%2A> selezione compilerà tutto il pannello. Se la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà è impostata, l'immagine verrà visualizzata dietro i controlli contenuti nel pannello.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo. Per informazioni su come configurare tale progetto in Visual Studio, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Impostare lo sfondo nell'Progettazione Windows Form

1. Aprire il progetto in Visual Studio e selezionare il <xref:System.Windows.Forms.Panel> controllo.

2. Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.

3. Selezionare la scheda **personalizzata** per visualizzare una tavolozza di colori.

4. Selezionare la scheda **Web** o **sistema** per visualizzare un elenco di nomi predefiniti per i colori, quindi selezionare un colore.

5. Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla <xref:System.Windows.Forms.Control.BackgroundImage%2A> Proprietà.

6. Nella finestra di dialogo **Apri** selezionare il file che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controllo del pannello](panel-control-windows-forms.md)
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
