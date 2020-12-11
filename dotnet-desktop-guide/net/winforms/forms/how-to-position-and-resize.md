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
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a><span data-ttu-id="271a1-104">Come posizionare e ridimensionare un form (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="271a1-104">How to position and size a form (Windows Forms .NET)</span></span>

<span data-ttu-id="271a1-105">Quando viene creato un modulo, le dimensioni e la posizione vengono inizialmente impostate su un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="271a1-105">When a form is created, the size and location is initially set to a default value.</span></span> <span data-ttu-id="271a1-106">Le dimensioni predefinite di un modulo sono in genere una larghezza e un'altezza pari a _800x500_ pixel.</span><span class="sxs-lookup"><span data-stu-id="271a1-106">The default size of a form is generally a width and height of _800x500_ pixels.</span></span> <span data-ttu-id="271a1-107">Il percorso iniziale, quando il modulo viene visualizzato, dipende da alcune impostazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="271a1-107">The initial location, when the form is displayed, depends on a few different settings.</span></span>

<span data-ttu-id="271a1-108">È possibile modificare le dimensioni di un modulo in fase di progettazione con Visual Studio e in fase di esecuzione con il codice.</span><span class="sxs-lookup"><span data-stu-id="271a1-108">You can change the size of a form at design time with Visual Studio, and at run time with code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a><span data-ttu-id="271a1-109">Ridimensionare con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="271a1-109">Resize with the designer</span></span>

<span data-ttu-id="271a1-110">[Una volta aggiunto un nuovo modulo](how-to-add.md) al progetto, le dimensioni di un modulo vengono impostate in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="271a1-110">After [adding a new form](how-to-add.md) to the project, the size of a form is set in two different ways.</span></span> <span data-ttu-id="271a1-111">Per prima cosa, è possibile impostarla con le dimensioni dei grip nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="271a1-111">First, you can set it is with the size grips in the designer.</span></span> <span data-ttu-id="271a1-112">Trascinando il bordo destro, il bordo inferiore o l'angolo, è possibile ridimensionare il form.</span><span class="sxs-lookup"><span data-stu-id="271a1-112">By dragging either the right edge, bottom edge, or the corner, you can resize the form.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere un nuovo modulo al progetto Windows Form con i grip":::

<span data-ttu-id="271a1-114">Il secondo modo in cui è possibile ridimensionare il form mentre è aperta la finestra di progettazione si trova nel riquadro proprietà.</span><span class="sxs-lookup"><span data-stu-id="271a1-114">The second way you can resize the form while the designer is open, is through the properties pane.</span></span> <span data-ttu-id="271a1-115">Selezionare il modulo, quindi trovare il riquadro **Proprietà** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="271a1-115">Select the form, then find the **Properties** pane in Visual Studio.</span></span> <span data-ttu-id="271a1-116">Scorrere verso il basso fino a **ridimensionarlo** ed espanderlo.</span><span class="sxs-lookup"><span data-stu-id="271a1-116">Scroll down to **size** and expand it.</span></span> <span data-ttu-id="271a1-117">È possibile impostare la **larghezza** e l' **altezza** manualmente.</span><span class="sxs-lookup"><span data-stu-id="271a1-117">You can set the **Width** and **Height** manually.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere nuovo modulo al progetto Windows Form":::

## <a name="resize-in-code"></a><span data-ttu-id="271a1-119">Ridimensiona nel codice</span><span class="sxs-lookup"><span data-stu-id="271a1-119">Resize in code</span></span>

<span data-ttu-id="271a1-120">Anche se la finestra di progettazione imposta la dimensione iniziale di un form, è possibile ridimensionarla tramite codice.</span><span class="sxs-lookup"><span data-stu-id="271a1-120">Even though the designer sets the starting size of a form, you can resize it through code.</span></span> <span data-ttu-id="271a1-121">L'uso del codice per ridimensionare un form è utile quando un elemento dell'applicazione determina che le dimensioni predefinite del modulo non sono sufficienti.</span><span class="sxs-lookup"><span data-stu-id="271a1-121">Using code to resize a form is useful when something about your application determines that the default size of the form is insufficient.</span></span>

<span data-ttu-id="271a1-122">Per ridimensionare un form, modificare <xref:System.Windows.Forms.Form.Size%2A> , che rappresenta la larghezza e l'altezza del form.</span><span class="sxs-lookup"><span data-stu-id="271a1-122">To resize a form, change the <xref:System.Windows.Forms.Form.Size%2A>, which represents the width and height of the form.</span></span>

### <a name="resize-the-current-form"></a><span data-ttu-id="271a1-123">Ridimensiona il form corrente</span><span class="sxs-lookup"><span data-stu-id="271a1-123">Resize the current form</span></span>

<span data-ttu-id="271a1-124">È possibile modificare le dimensioni del form corrente purché il codice sia in esecuzione nel contesto del modulo.</span><span class="sxs-lookup"><span data-stu-id="271a1-124">You can change the size of the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="271a1-125">Se, ad esempio, è presente `Form1` un pulsante, quando si fa clic richiama il `Click` gestore eventi per ridimensionare il form:</span><span class="sxs-lookup"><span data-stu-id="271a1-125">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler to resize the form:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a><span data-ttu-id="271a1-126">Ridimensionare un modulo diverso</span><span class="sxs-lookup"><span data-stu-id="271a1-126">Resize a different form</span></span>

<span data-ttu-id="271a1-127">È possibile modificare le dimensioni di un altro form dopo che è stato creato usando la variabile che fa riferimento al modulo.</span><span class="sxs-lookup"><span data-stu-id="271a1-127">You can change the size of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="271a1-128">Si immagini, ad esempio, di avere due moduli `Form1` (il modulo di avvio in questo esempio) e `Form2` .</span><span class="sxs-lookup"><span data-stu-id="271a1-128">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="271a1-129">`Form1` dispone di un pulsante che, se selezionato, richiama l' `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="271a1-129">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="271a1-130">Il gestore di questo evento crea una nuova istanza del `Form2` form, ne imposta la dimensione e quindi la Visualizza:</span><span class="sxs-lookup"><span data-stu-id="271a1-130">The handler of this event creates a new instance of the `Form2` form, sets the size, and then displays it:</span></span>

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

<span data-ttu-id="271a1-131">Se `Size` non è impostato manualmente, le dimensioni predefinite del modulo corrispondono a quelle impostate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="271a1-131">If the `Size` isn't manually set, the form's default size is what it was set to during design-time.</span></span>

## <a name="position-with-the-designer"></a><span data-ttu-id="271a1-132">Posizionare con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="271a1-132">Position with the designer</span></span>

<span data-ttu-id="271a1-133">Quando viene creata e visualizzata un'istanza del modulo, la posizione iniziale del form è determinata dalla <xref:System.Windows.Forms.Form.StartPosition%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="271a1-133">When a form instance is created and displayed, the initial location of the form is determined by the <xref:System.Windows.Forms.Form.StartPosition%2A> property.</span></span> <span data-ttu-id="271a1-134">La <xref:System.Windows.Forms.Form.Location%2A> proprietà include la posizione corrente del form.</span><span class="sxs-lookup"><span data-stu-id="271a1-134">The <xref:System.Windows.Forms.Form.Location%2A> property holds the current location the form.</span></span> <span data-ttu-id="271a1-135">Entrambe le proprietà possono essere impostate tramite la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="271a1-135">Both properties can be set through the designer.</span></span>

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="riquadro delle proprietà di Visual Studio con la posizione iniziale evidenziata":::

| <span data-ttu-id="271a1-137">Enumerazione FormStartPosition</span><span class="sxs-lookup"><span data-stu-id="271a1-137">FormStartPosition Enum</span></span> | <span data-ttu-id="271a1-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="271a1-138">Description</span></span>                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="271a1-139">CenterParent</span><span class="sxs-lookup"><span data-stu-id="271a1-139">CenterParent</span></span>           | <span data-ttu-id="271a1-140">Il form risulta centrato rispetto al relativo form padre.</span><span class="sxs-lookup"><span data-stu-id="271a1-140">The form is centered within the bounds of its parent form.</span></span>                                                       |
| <span data-ttu-id="271a1-141">CenterScreen</span><span class="sxs-lookup"><span data-stu-id="271a1-141">CenterScreen</span></span>           | <span data-ttu-id="271a1-142">Il modulo viene centrato sulla visualizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="271a1-142">The form is centered on the current display.</span></span>                                                                     |
| <span data-ttu-id="271a1-143">Manuale</span><span class="sxs-lookup"><span data-stu-id="271a1-143">Manual</span></span>                 | <span data-ttu-id="271a1-144">La posizione del form è determinata dalla proprietà [location](xref:System.Windows.Forms.Form.Location%2A) .</span><span class="sxs-lookup"><span data-stu-id="271a1-144">The position of the form is determined by the [Location](xref:System.Windows.Forms.Form.Location%2A) property.</span></span>   |
| <span data-ttu-id="271a1-145">WindowsDefaultBounds</span><span class="sxs-lookup"><span data-stu-id="271a1-145">WindowsDefaultBounds</span></span>   | <span data-ttu-id="271a1-146">Il modulo viene posizionato nel percorso predefinito di Windows e viene ridimensionato in base alle dimensioni predefinite determinate da Windows.</span><span class="sxs-lookup"><span data-stu-id="271a1-146">The form is positioned at the Windows default location and is resized to the default size determined by Windows.</span></span> |
| <span data-ttu-id="271a1-147">WindowsDefaultLocation</span><span class="sxs-lookup"><span data-stu-id="271a1-147">WindowsDefaultLocation</span></span> | <span data-ttu-id="271a1-148">Il modulo viene posizionato nel percorso predefinito di Windows e non viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="271a1-148">The form is positioned at the Windows default location and isn't resized.</span></span>                                        |

<span data-ttu-id="271a1-149">Il valore [CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) funziona solo con i form che sono un form figlio MDI (Multiple Document Interface) o un formato normale che viene visualizzato con il <xref:System.Windows.Window.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="271a1-149">The [CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) value only works with forms that are either a multiple document interface (MDI) child form, or a normal form that is displayed with the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="271a1-150">`CenterParent` non ha alcun effetto su un form normale che viene visualizzato con il <xref:System.Windows.Window.Show%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="271a1-150">`CenterParent` has no affect on a normal form that is displayed with the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="271a1-151">Per centrare un form ( `form` variabile) a un altro form ( `parentForm` variabile), usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="271a1-151">To center a form (`form` variable) to another form (`parentForm` variable), use the following code:</span></span>

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

## <a name="position-with-code"></a><span data-ttu-id="271a1-152">Posizione con codice</span><span class="sxs-lookup"><span data-stu-id="271a1-152">Position with code</span></span>

<span data-ttu-id="271a1-153">Anche se la finestra di progettazione può essere usata per impostare la posizione iniziale di un modulo, è possibile usare il codice per modificare la modalità di avvio o impostare manualmente il percorso.</span><span class="sxs-lookup"><span data-stu-id="271a1-153">Even though the designer can be used to set the starting location of a form, you can use code either change the starting position mode or set the location manually.</span></span> <span data-ttu-id="271a1-154">Usare il codice per posizionare un form è utile se è necessario posizionare e ridimensionare manualmente un form in relazione alla schermata o ad altri moduli.</span><span class="sxs-lookup"><span data-stu-id="271a1-154">Using code to position a form is useful if you need to manually position and size a form in relation to the screen or other forms.</span></span>

### <a name="move-the-current-form"></a><span data-ttu-id="271a1-155">Spostare il form corrente</span><span class="sxs-lookup"><span data-stu-id="271a1-155">Move the current form</span></span>

<span data-ttu-id="271a1-156">È possibile spostare il form corrente fino a quando il codice è in esecuzione nel contesto del modulo.</span><span class="sxs-lookup"><span data-stu-id="271a1-156">You can move the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="271a1-157">Se, ad esempio, si dispone `Form1` di un pulsante, quando si fa clic su richiama il `Click` gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="271a1-157">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler.</span></span> <span data-ttu-id="271a1-158">Il gestore in questo esempio imposta la posizione del form sulla parte superiore sinistra dello schermo impostando la <xref:System.Windows.Forms.Form.Location%2A> proprietà:</span><span class="sxs-lookup"><span data-stu-id="271a1-158">The handler in this example changes the location of the form to the top-left of the screen by setting the <xref:System.Windows.Forms.Form.Location%2A> property:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a><span data-ttu-id="271a1-159">Posizionare un modulo diverso</span><span class="sxs-lookup"><span data-stu-id="271a1-159">Position a different form</span></span>

<span data-ttu-id="271a1-160">È possibile modificare il percorso di un altro form dopo che è stato creato usando la variabile che fa riferimento al modulo.</span><span class="sxs-lookup"><span data-stu-id="271a1-160">You can change the location of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="271a1-161">Si immagini, ad esempio, di avere due moduli `Form1` (il modulo di avvio in questo esempio) e `Form2` .</span><span class="sxs-lookup"><span data-stu-id="271a1-161">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="271a1-162">`Form1` dispone di un pulsante che, se selezionato, richiama l' `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="271a1-162">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="271a1-163">Il gestore di questo evento crea una nuova istanza del `Form2` form e imposta le dimensioni:</span><span class="sxs-lookup"><span data-stu-id="271a1-163">The handler of this event creates a new instance of the `Form2` form and sets the size:</span></span>

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

<span data-ttu-id="271a1-164">Se `Size` non è impostato, le dimensioni predefinite del modulo corrispondono a quelle impostate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="271a1-164">If the `Size` isn't set, the form's default size is what it was set to at design-time.</span></span>

## <a name="see-also"></a><span data-ttu-id="271a1-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="271a1-165">See also</span></span>

- [<span data-ttu-id="271a1-166">Come aggiungere un modulo a un progetto (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="271a1-166">How to add a form to a project (Windows Forms .NET)</span></span>](how-to-add.md)
- [<span data-ttu-id="271a1-167">Cenni preliminari sugli eventi (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="271a1-167">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="271a1-168">Posizione e layout dei controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="271a1-168">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)
