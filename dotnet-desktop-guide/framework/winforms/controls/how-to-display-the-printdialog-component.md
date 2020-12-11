---
title: Come visualizzare il componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961843"
---
# <a name="how-to-display-the-printdialog-component"></a>Come visualizzare il componente PrintDialog

Il <xref:System.Windows.Forms.PrintDialog> componente è la finestra di dialogo di stampa standard di Windows a cui molti utenti hanno familiarità. Poiché gli utenti saranno immediatamente confortevoli, potrebbe essere utile utilizzare il <xref:System.Windows.Forms.PrintDialog> componente.

## <a name="to-display-the-printdialog-component"></a>Per visualizzare il componente PrintDialog

- Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo dall'interno del codice dell'applicazione.

     Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa. Questi vengono salvati nella  <xref:System.Drawing.Printing.PrinterSettings> classe (e la <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede al [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) tramite il <xref:System.Windows.Forms.PrintDialog> componente) associato al processo di stampa. Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.

## <a name="see-also"></a>Vedere anche

- [Procedura: Creare processi di stampa standard per Windows Form](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Procedura: Acquisire l'input dell'utente da un componente PrintDialog in fase di esecuzione](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Componente PrintDialog](printdialog-component-windows-forms.md)
- [Supporto per la stampa in Windows Form](../advanced/windows-forms-print-support.md)
- [Controlli di Windows Forms](index.md)
