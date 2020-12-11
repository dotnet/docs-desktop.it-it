---
title: 'Procedura: Visualizzare la Guida rapida'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: a3b40f49119fcf7900f1f0c8b77c5d83fe81144c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951454"
---
# <a name="how-to-display-pop-up-help"></a>Procedura: visualizzare la Guida popup

Un modo per visualizzare la Guida in Windows Forms è tramite **il pulsante** ?, situato sul lato destro della barra del titolo, accessibile tramite la <xref:System.Windows.Forms.Form.HelpButton%2A> Proprietà. Questo tipo di visualizzazione della Guida è ideale con le finestre di dialogo. Con le finestre di dialogo visualizzate come modali (con il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>) risulta difficile accedere a sistemi di Guida esterni, perché le finestre di dialogo modali devono venire chiuse prima che lo stato attivo possa passare a un'altra finestra. Inoltre, per usare **il pulsante** ? è necessario che nella barra del titolo non sia presente un pulsante di **riduzione a icona** o un pulsante **Ingrandisci** . Si tratta di una convenzione della finestra di dialogo standard, mentre i moduli in genere dispongono di pulsanti **Riduci a icona** e **Ingrandisci** .

È anche possibile usare il <xref:System.Windows.Forms.HelpProvider> componente per collegare i controlli ai file in un sistema di guida, anche se è stata implementata la Guida popup. Per ulteriori informazioni, vedere [la Guida in un'applicazione Windows](how-to-provide-help-in-a-windows-application.md).

## <a name="display-pop-up-help"></a>Visualizza la Guida popup

1. In Visual Studio trascinare un componente [HelpProvider](../controls/helpprovider-component-windows-forms.md) dalla casella degli strumenti al form.

   Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.

2. Nella finestra Proprietà impostare la proprietà <xref:System.Windows.Forms.Form.HelpButton%2A> su `true`. Sulla destra della barra del titolo del form verrà visualizzato un pulsante con un punto interrogativo.

3. Per visualizzare <xref:System.Windows.Forms.Form.HelpButton%2A>, è necessario impostare le proprietà <xref:System.Windows.Forms.Form.MinimizeBox%2A> e <xref:System.Windows.Forms.Form.MaximizeBox%2A> del form su `false`, la proprietà <xref:System.Windows.Forms.Form.ControlBox%2A> su `true` e la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> su uno dei valori seguenti: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.

4. Selezionare il controllo per il quale si desidera visualizzare la Guida nel form e impostare la stringa della Guida nella finestra Proprietà. Si tratta della stringa di testo che verrà visualizzata in una finestra simile a una [Descrizione comando](../controls/tooltip-component-windows-forms.md).

5. Premere **F5**.

6. Premere il **pulsante? sulla barra del titolo** e fare clic sul controllo in cui è stata impostata la stringa della guida.

## <a name="see-also"></a>Vedere anche

- [Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi](control-help-using-tooltips.md)
- [Integrazione della Guida dell'utente in Windows Form](integrating-user-help-in-windows-forms.md)
- [WinForms](../index.yml)
