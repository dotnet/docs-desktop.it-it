---
title: 'Procedura: Visualizzare una tavolozza dei colori con il componente ColorDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964864"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Procedura: Visualizzare una tavolozza dei colori con il componente ColorDialog
Il componente [ColorDialog](colordialog-component-windows-forms.md) Visualizza una tavolozza di colori e restituisce una proprietà contenente il colore selezionato dall'utente.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Per scegliere un colore utilizzando il componente ColorDialog  
  
1. Consente di visualizzare la finestra di dialogo utilizzando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.  
  
2. Utilizzare la <xref:System.Windows.Forms.DialogResult> proprietà per determinare la modalità di chiusura della finestra di dialogo.  
  
3. Utilizzare la <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà del <xref:System.Windows.Forms.ColorDialog> componente per impostare il colore scelto.  
  
     Nell'esempio seguente il <xref:System.Windows.Forms.Button> gestore eventi del controllo <xref:System.Windows.Forms.Control.Click> apre un <xref:System.Windows.Forms.ColorDialog> componente. Quando si sceglie un colore e l'utente fa clic su **OK**, il <xref:System.Windows.Forms.Button> colore di sfondo del controllo viene impostato sul colore scelto. Nell'esempio si presuppone che il form disponga di un <xref:System.Windows.Forms.Button> controllo e di un <xref:System.Windows.Forms.ColorDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
