---
title: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966055"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Forms
Il <xref:System.Windows.Forms.RichTextBox> controllo Windows Forms dispone di numerose opzioni per la formattazione del testo visualizzato. È possibile formattare i paragrafi selezionati come elenchi puntati impostando la <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Proprietà. È anche possibile usare le <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> proprietà, e <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> per impostare il rientro dei paragrafi rispetto ai bordi sinistro e destro del controllo e il bordo sinistro di altre righe di testo.  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>Per formattare un paragrafo come elenco puntato  
  
1. Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> su `true`.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a>Per impostare il rientro di un paragrafo  
  
1. Impostare la <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> proprietà su un intero che rappresenta la distanza in pixel tra il bordo sinistro del controllo e il bordo sinistro del testo.  
  
2. Impostare la <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> proprietà su un intero che rappresenta la distanza in pixel tra il bordo sinistro della prima riga di testo nel paragrafo e il bordo sinistro delle righe successive nello stesso paragrafo. Il valore della <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> proprietà si applica solo alle righe in un paragrafo di cui è stato eseguito il wrapped sotto la prima riga.  
  
3. Impostare la <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> proprietà su un intero che rappresenta la distanza in pixel tra il bordo destro del controllo e il bordo destro del testo.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    > Tutte queste proprietà vengono applicate a qualsiasi paragrafo contenente il testo selezionato, oltre che al testo digitato dopo il punto di inserimento corrente. Ad esempio, quando un utente seleziona una parola all'interno di un paragrafo e ne regola il rientro, le nuove impostazioni verranno applicate all'intero paragrafo contenente tale parola, nonché agli eventuali paragrafi immessi successivamente dopo il paragrafo selezionato. Per informazioni sulla selezione di testo a livello di codice, vedere <xref:System.Windows.Forms.TextBoxBase.Select%2A> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
