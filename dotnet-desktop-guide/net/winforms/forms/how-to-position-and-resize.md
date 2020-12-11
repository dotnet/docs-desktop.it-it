---
title: Posizionare e ridimensionare un form
description: Informazioni su come impostare le dimensioni e la posizione di un modulo in .NET Windows Forms e Visual Studio. Le dimensioni e la posizione possono essere impostate nella finestra di progettazione di Visual Studio o tramite codice.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning Windows Forms
- resizing Windows Forms
- Windows Forms, location
- Windows Forms, size
ms.openlocfilehash: 4fdaff7589669ae2e216d08feda5368835b50b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969550"
---
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a>Come posizionare e ridimensionare un form (Windows Forms .NET)

Quando viene creato un modulo, le dimensioni e la posizione vengono inizialmente impostate su un valore predefinito. Le dimensioni predefinite di un modulo sono in genere una larghezza e un'altezza pari a _800x500_ pixel. Il percorso iniziale, quando il modulo viene visualizzato, dipende da alcune impostazioni diverse.

È possibile modificare le dimensioni di un modulo in fase di progettazione con Visual Studio e in fase di esecuzione con il codice.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a>Ridimensionare con la finestra di progettazione

[Una volta aggiunto un nuovo modulo](how-to-add.md) al progetto, le dimensioni di un modulo vengono impostate in due modi diversi. Per prima cosa, è possibile impostarla con le dimensioni dei grip nella finestra di progettazione. Trascinando il bordo destro, il bordo inferiore o l'angolo, è possibile ridimensionare il form.

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere un nuovo modulo al progetto Windows Form con i grip":::

Il secondo modo in cui è possibile ridimensionare il form mentre è aperta la finestra di progettazione si trova nel riquadro proprietà. Selezionare il modulo, quindi trovare il riquadro **Proprietà** in Visual Studio. Scorrere verso il basso fino a **ridimensionarlo** ed espanderlo. È possibile impostare la **larghezza** e l' **altezza** manualmente.

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere nuovo modulo al progetto Windows Form":::

## <a name="resize-in-code"></a>Ridimensiona nel codice

Anche se la finestra di progettazione imposta la dimensione iniziale di un form, è possibile ridimensionarla tramite codice. L'uso del codice per ridimensionare un form è utile quando un elemento dell'applicazione determina che le dimensioni predefinite del modulo non sono sufficienti.

Per ridimensionare un form, modificare <xref:System.Windows.Forms.Form.Size%2A> , che rappresenta la larghezza e l'altezza del form.

### <a name="resize-the-current-form"></a>Ridimensiona il form corrente

È possibile modificare le dimensioni del form corrente purché il codice sia in esecuzione nel contesto del modulo. Se, ad esempio, è presente `Form1` un pulsante, quando si fa clic richiama il `Click` gestore eventi per ridimensionare il form:

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a>Ridimensionare un modulo diverso

È possibile modificare le dimensioni di un altro form dopo che è stato creato usando la variabile che fa riferimento al modulo. Si immagini, ad esempio, di avere due moduli `Form1` (il modulo di avvio in questo esempio) e `Form2` . `Form1` dispone di un pulsante che, se selezionato, richiama l' `Click` evento. Il gestore di questo evento crea una nuova istanza del `Form2` form, ne imposta la dimensione e quindi la Visualizza:

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

Se `Size` non è impostato manualmente, le dimensioni predefinite del modulo corrispondono a quelle impostate in fase di progettazione.

## <a name="position-with-the-designer"></a>Posizionare con la finestra di progettazione

Quando viene creata e visualizzata un'istanza del modulo, la posizione iniziale del form è determinata dalla <xref:System.Windows.Forms.Form.StartPosition%2A> Proprietà. La <xref:System.Windows.Forms.Form.Location%2A> proprietà include la posizione corrente del form. Entrambe le proprietà possono essere impostate tramite la finestra di progettazione.

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="riquadro delle proprietà di Visual Studio con la posizione iniziale evidenziata":::

| Enumerazione FormStartPosition | Descrizione                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| CenterParent           | Il form risulta centrato rispetto al relativo form padre.                                                       |
| CenterScreen           | Il modulo viene centrato sulla visualizzazione corrente.                                                                     |
| Manuale                 | La posizione del form è determinata dalla proprietà [location](xref:System.Windows.Forms.Form.Location%2A) .   |
| WindowsDefaultBounds   | Il modulo viene posizionato nel percorso predefinito di Windows e viene ridimensionato in base alle dimensioni predefinite determinate da Windows. |
| WindowsDefaultLocation | Il modulo viene posizionato nel percorso predefinito di Windows e non viene ridimensionato.                                        |

Il valore [CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) funziona solo con i form che sono un form figlio MDI (Multiple Document Interface) o un formato normale che viene visualizzato con il <xref:System.Windows.Window.ShowDialog%2A> metodo. `CenterParent` non ha alcun effetto su un form normale che viene visualizzato con il <xref:System.Windows.Window.Show%2A> metodo. Per centrare un form ( `form` variabile) a un altro form ( `parentForm` variabile), usare il codice seguente:

```csharp
form.StartPosition = FormStartPosition.Manual;
form.Location = new Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                          parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y);
form.Show();
```

```vb
form.StartPosition = Windows.Forms.FormStartPosition.CenterParent.Manual
form.Location = New Drawing.Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                                  parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y)

form.Show()
```

## <a name="position-with-code"></a>Posizione con codice

Anche se la finestra di progettazione può essere usata per impostare la posizione iniziale di un modulo, è possibile usare il codice per modificare la modalità di avvio o impostare manualmente il percorso. Usare il codice per posizionare un form è utile se è necessario posizionare e ridimensionare manualmente un form in relazione alla schermata o ad altri moduli.

### <a name="move-the-current-form"></a>Spostare il form corrente

È possibile spostare il form corrente fino a quando il codice è in esecuzione nel contesto del modulo. Se, ad esempio, si dispone `Form1` di un pulsante, quando si fa clic su richiama il `Click` gestore eventi. Il gestore in questo esempio imposta la posizione del form sulla parte superiore sinistra dello schermo impostando la <xref:System.Windows.Forms.Form.Location%2A> proprietà:

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a>Posizionare un modulo diverso

È possibile modificare il percorso di un altro form dopo che è stato creato usando la variabile che fa riferimento al modulo. Si immagini, ad esempio, di avere due moduli `Form1` (il modulo di avvio in questo esempio) e `Form2` . `Form1` dispone di un pulsante che, se selezionato, richiama l' `Click` evento. Il gestore di questo evento crea una nuova istanza del `Form2` form e imposta le dimensioni:

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

Se `Size` non è impostato, le dimensioni predefinite del modulo corrispondono a quelle impostate in fase di progettazione.

## <a name="see-also"></a>Vedere anche

- [Come aggiungere un modulo a un progetto (Windows Forms .NET)](how-to-add.md)
- [Cenni preliminari sugli eventi (Windows Forms .NET)](events.md)
- [Posizione e layout dei controlli (Windows Forms .NET)](../controls/layout.md)
