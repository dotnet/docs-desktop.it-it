---
title: Panoramica del controllo TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960925"
---
# <a name="textbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo TextBox (Windows Form)
Windows Forms caselle di testo vengono utilizzate per ottenere l'input dall'utente o per visualizzare il testo. Il <xref:System.Windows.Forms.TextBox> controllo viene in genere usato per testo modificabile, anche se può essere reso di sola lettura. Le caselle di testo possono visualizzare più righe, eseguire il wrapping del testo sulle dimensioni del controllo e aggiungere la formattazione di base. Il <xref:System.Windows.Forms.TextBox> controllo fornisce un unico stile di formato per il testo visualizzato o immesso nel controllo. Per visualizzare più tipi di testo formattato, usare il <xref:System.Windows.Forms.RichTextBox> controllo. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo RichTextBox](richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Utilizzo del controllo TextBox  
 Il testo visualizzato dal controllo è contenuto nella <xref:System.Windows.Forms.TextBox.Text%2A> Proprietà. Per impostazione predefinita, è possibile immettere fino a 2048 caratteri in una casella di testo. Se si imposta la <xref:System.Windows.Forms.TextBox.Multiline%2A> proprietà su `true` , è possibile immettere fino a 32 KB di testo. La <xref:System.Windows.Forms.TextBox.Text%2A> proprietà può essere impostata in fase di progettazione con la finestra Proprietà, in fase di esecuzione nel codice o in base all'input dell'utente in fase di esecuzione. Il contenuto corrente di una casella di testo può essere recuperato in fase di esecuzione leggendo la <xref:System.Windows.Forms.TextBox.Text%2A> Proprietà.  
  
 Nell'esempio di codice seguente viene impostato il testo nel controllo in fase di esecuzione. La `InitializeMyControl` stored procedure non verrà eseguita automaticamente, ma deve essere chiamata.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox di Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
