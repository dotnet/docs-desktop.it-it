---
title: Panoramica del controllo RichTextBox
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964297"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo RichTextBox (Windows Form)
Il <xref:System.Windows.Forms.RichTextBox> controllo Windows Forms viene usato per visualizzare, immettere e modificare il testo con la formattazione. Il <xref:System.Windows.Forms.RichTextBox> controllo esegue tutte le operazioni del <xref:System.Windows.Forms.TextBox> controllo, ma può anche visualizzare i tipi di carattere, i colori e i collegamenti, caricare testo e immagini incorporate da un file e trovare i caratteri specificati. Il <xref:System.Windows.Forms.RichTextBox> controllo viene in genere usato per fornire funzionalità di visualizzazione e manipolazione del testo simili alle applicazioni di elaborazione di Word, ad esempio Microsoft Word. Analogamente al <xref:System.Windows.Forms.TextBox> controllo, il <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare le barre di scorrimento. tuttavia <xref:System.Windows.Forms.TextBox> , a differenza del controllo, l'impostazione predefinita prevede la visualizzazione di barre di scorrimento orizzontali e verticali in base alle esigenze e altre impostazioni della barra di scorrimento.  
  
## <a name="working-with-the-richtextbox-control"></a>Utilizzo del controllo RichTextBox  
 Come per il <xref:System.Windows.Forms.TextBox> controllo, il testo visualizzato viene impostato dalla <xref:System.Windows.Forms.RichTextBox.Text%2A> Proprietà. Il <xref:System.Windows.Forms.RichTextBox> controllo dispone di numerose proprietà per formattare il testo. Per informazioni dettagliate su queste proprietà, vedere [Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) e [Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox Windows Form](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Per modificare i file, <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> i <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodi e consentono di visualizzare e scrivere più formati di file, tra cui testo normale, testo normale Unicode e RTF (Rich Text Format). I formati di file possibili sono elencati in <xref:System.Windows.Forms.RichTextBoxStreamType> . È possibile usare il <xref:System.Windows.Forms.RichTextBox.Find%2A> metodo per trovare stringhe di testo o caratteri specifici.  
  
 È anche possibile usare un <xref:System.Windows.Forms.RichTextBox> controllo per i collegamenti di tipo Web impostando la <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> proprietà su `true` e scrivendo codice per gestire l' <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento. Per altre informazioni, vedere [Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). È possibile impedire all'utente di modificare parte o tutto il testo nel controllo impostando la <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> proprietà su `true` .  
  
 È possibile annullare e ripetere la maggior parte delle operazioni di modifica in un <xref:System.Windows.Forms.RichTextBox> controllo chiamando i <xref:System.Windows.Forms.TextBoxBase.Undo%2A> <xref:System.Windows.Forms.RichTextBox.Redo%2A> metodi e. Il <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> metodo consente di determinare se l'ultima operazione annullata dall'utente può essere riapplicata al controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Panoramica del controllo TextBox](textbox-control-overview-windows-forms.md)
