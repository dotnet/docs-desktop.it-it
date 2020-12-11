---
title: Panoramica del controllo RadioButton
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965905"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Cenni preliminari sul controllo RadioButton (Windows Form)
<xref:System.Windows.Forms.RadioButton>I controlli Windows Forms presentano un set di due o più scelte che si escludono a vicenda per l'utente. Mentre i pulsanti di opzione e le caselle di controllo sembrano funzionare in modo analogo, esiste una differenza importante: quando un utente seleziona un pulsante di opzione, non è possibile selezionare anche gli altri pulsanti di opzione nello stesso gruppo. Al contrario, è possibile selezionare qualsiasi numero di caselle di controllo. La definizione di un gruppo di pulsanti di opzione indica all'utente "Ecco un set di opzioni da cui è possibile scegliere una sola e una sola".  
  
## <a name="using-the-control"></a>Uso del controllo  
 Quando <xref:System.Windows.Forms.RadioButton> si fa clic su un controllo, la <xref:System.Windows.Forms.RadioButton.Checked%2A> proprietà viene impostata su `true` e <xref:System.Windows.Forms.Control.Click> viene chiamato il gestore eventi. L' <xref:System.Windows.Forms.RadioButton.CheckedChanged> evento viene generato quando cambia il valore della <xref:System.Windows.Forms.RadioButton.Checked%2A> Proprietà. Se la <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> proprietà è impostata su `true` (impostazione predefinita), quando si seleziona il pulsante di opzione tutti gli altri elementi del gruppo vengono cancellati automaticamente. Questa proprietà viene in genere impostata su solo `false` quando viene utilizzato il codice di convalida per verificare che il pulsante di opzione selezionato sia un'opzione consentita. Il testo visualizzato all'interno del controllo viene impostato con la <xref:System.Windows.Forms.Control.Text%2A> proprietà, che può contenere tasti di scelta rapida. Una chiave di accesso consente a un utente di fare clic sul controllo premendo il tasto ALT con il tasto di accesso. Per altre informazioni, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md) e [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Il <xref:System.Windows.Forms.RadioButton> controllo può apparire come un pulsante di comando, che sembra essere stato premuto se selezionato, se la <xref:System.Windows.Forms.RadioButton.Appearance%2A> proprietà è impostata su <xref:System.Windows.Forms.Appearance.Button> . I pulsanti di opzione possono anche visualizzare immagini usando le <xref:System.Windows.Forms.ButtonBase.Image%2A> <xref:System.Windows.Forms.ButtonBase.ImageList%2A> proprietà e. Per altre informazioni, vedere [procedura: impostare l'immagine visualizzata da un controllo Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RadioButton>
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
- [Panoramica del controllo GroupBox](groupbox-control-overview-windows-forms.md)
- [Panoramica del controllo CheckBox](checkbox-control-overview-windows-forms.md)
- [Procedura: creare tasti di scelta per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md)
- [Procedura: impostare il testo visualizzato da un controllo di Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Procedura: Raggruppare i controlli RadioButton di Windows Forms in modo che funzionino come set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [Controllo RadioButton](radiobutton-control-windows-forms.md)
