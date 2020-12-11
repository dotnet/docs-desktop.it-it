---
title: 'Procedura: Creare testo di dimensioni variabili in un controllo ComboBox'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: acc5ee47536772d98fcfe98849335933c24a41d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961927"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>Procedura: Creare testo di dimensioni variabili in un controllo ComboBox
In questo esempio viene illustrato il disegno personalizzato del testo in un <xref:System.Windows.Forms.ComboBox> controllo. Quando un elemento soddisfa determinati criteri, viene disegnato in un tipo di carattere più grande e trasformato in rosso.

## <a name="example"></a>Esempio

```vb
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)
    Dim siText As SizeF

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _
lFont)
    Else
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)
    End If

    e.ItemHeight = siText.Height
    e.ItemWidth = siText.Width
End Sub

Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem
    Dim g As Graphics = e.Graphics
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _
e.Bounds.X, e.Bounds.Y)
    Else
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)
    End If
End Sub
```

## <a name="compiling-the-code"></a>Compilazione del codice
 L'esempio presenta i requisiti seguenti:

- Windows Form.

- <xref:System.Windows.Forms.ComboBox>Controllo denominato `ListBox1` con tre elementi nella <xref:System.Windows.Forms.ComboBox.Items%2A> Proprietà. In questo esempio, i tre elementi sono denominati `"One", Two", and Three"` . La <xref:System.Windows.Forms.ComboBox.DrawMode%2A> proprietà di `ComboBox1` deve essere impostata su <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> .

    > [!NOTE]
    > Questa tecnica è applicabile anche al <xref:System.Windows.Forms.ListBox> controllo: è possibile sostituire un <xref:System.Windows.Forms.ListBox> per <xref:System.Windows.Forms.ComboBox> .

- Riferimenti agli spazi dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [Controlli con supporto incorporato per la creazione da parte del proprietario](controls-with-built-in-owner-drawing-support.md)
- [Controllo ListBox](listbox-control-windows-forms.md)
- [Controllo ComboBox](combobox-control-windows-forms.md)
