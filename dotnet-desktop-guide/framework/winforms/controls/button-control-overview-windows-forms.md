---
title: Panoramica del controllo Button
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962956"
---
# <a name="button-control-overview-windows-forms"></a>Cenni preliminari sul controllo Button (Windows Form)
Il controllo <xref:System.Windows.Forms.Button> Windows Form consente all'utente di eseguire le operazioni desiderate facendo clic su di esso. Una volta scelto, il pulsante viene visualizzato come se fosse stato effettivamente premuto e poi rilasciato. Ogni volta che l'utente fa clic su un pulsante, <xref:System.Windows.Forms.Control.Click> viene richiamato il gestore eventi. <xref:System.Windows.Forms.Control.Click>Per eseguire qualsiasi azione scelta, inserire il codice nel gestore eventi.  
  
 Il testo visualizzato sul pulsante è contenuto nella <xref:System.Windows.Forms.Control.Text%2A> Proprietà. Se il testo supera la larghezza del pulsante, verrà eseguito il wrapping alla riga successiva. Tuttavia, verrà ritagliata se il controllo non può contenere l'altezza complessiva. Per altre informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md). La <xref:System.Windows.Forms.Control.Text%2A> proprietà può contenere una chiave di accesso, che consente a un utente di fare clic sul controllo premendo il tasto Alt con il tasto di accesso. Per informazioni dettagliate, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md). L'aspetto del testo è controllato dalla <xref:System.Windows.Forms.Control.Font%2A> proprietà e dalla <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> Proprietà.  
  
 Il <xref:System.Windows.Forms.Button> controllo può anche visualizzare immagini usando le <xref:System.Windows.Forms.ButtonBase.Image%2A> <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà e. Per altre informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Procedura: rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
