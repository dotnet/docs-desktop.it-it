---
title: Esercitazione su come creare una nuova app con Visual Studio
description: Seguire questa esercitazione per informazioni su come creare una nuova app Windows Forms per .NET con Visual Studio 2019.
ms.date: 10/26/2020
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: db0712aa642e54373f686fdd24a4747bf2d195e3
ms.sourcegitcommit: e8e3f6f23b5ddf9f5c4fe1ec5f6e0a8a609d49c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "97004732"
---
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a>Esercitazione: creare una nuova app WinForms (Windows Forms .NET)

In questa breve esercitazione si apprenderà come creare una nuova app Windows Forms (WinForms) con Visual Studio. Una volta generata l'app iniziale, si apprenderà come aggiungere controlli e come gestire gli eventi. Al termine di questa esercitazione, si disporrà di una semplice app che aggiunge nomi a una casella di riepilogo.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> - Creare una nuova app WinForms
> - Aggiungere controlli a un form
> - Gestire gli eventi di controllo per fornire la funzionalità dell'app
> - Eseguire l'app

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,8 o versioni successive](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - Selezionare il [carico di lavoro di Visual Studio Desktop](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)
  - Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)

## <a name="create-a-winforms-app"></a>Creare un'app WinForms

Il primo passaggio per creare una nuova app è l'apertura di Visual Studio e la generazione dell'app da un modello.

01. Aprire Visual Studio.
01. Selezionare **Crea un nuovo progetto**.

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Creare un nuovo progetto di Windows Forms in Visual Studio 2019 per .NET":::

01. Nella casella **Cerca modelli** Digitare **WinForms**, quindi premere <kbd>invio</kbd>.
01. Nell'elenco a discesa **linguaggio codice** scegliere **C#** o **Visual Basic**.
01. Nell'elenco modelli selezionare **Windows Forms app (.NET)** , quindi fare clic su **Avanti**.

    > [!IMPORTANT]
    > Non selezionare il modello **App Windows Forms (.NET _Framework_)** .

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="Cercare il modello di Windows Forms in Visual Studio 2019 per .NET":::

01. Nella finestra **Configura nuovo progetto** impostare il **nome del progetto** su **nomi** e fare clic su **Crea**.

    È anche possibile salvare il progetto in una cartella diversa modificando l'impostazione del **percorso** .

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="Configurare un nuovo progetto di Windows Forms in Visual Studio 2019 per .NET":::

Una volta generata l'app, Visual Studio dovrebbe aprire il riquadro della finestra di progettazione per il form predefinito _Form1_. Se la finestra di progettazione dei form non è visibile, fare doppio clic sul form nel riquadro **Esplora soluzioni** per aprire la finestra di progettazione.

### <a name="important-parts-of-visual-studio"></a>Parti importanti di Visual Studio

Il supporto per WinForms in Visual Studio include quattro componenti importanti con cui si interagirà quando si crea un'app:

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="I componenti importanti di Visual Studio da tenere presente durante la creazione di un progetto di Windows Forms per .NET":::

01. Esplora soluzioni

    Tutti i file di progetto, il codice, i moduli e le risorse verranno visualizzati in questo riquadro.

02. Proprietà

    Questo riquadro Mostra le impostazioni delle proprietà che è possibile configurare in base all'elemento selezionato. Se, ad esempio, si seleziona un elemento da **Esplora soluzioni**, verranno visualizzate le impostazioni delle proprietà correlate al file. Se si seleziona un oggetto nella **finestra di progettazione**, verranno visualizzate le impostazioni per il controllo o il form.

03. Progettazione form

    Si tratta della finestra di progettazione per il form. È interattivo ed è possibile trascinare gli oggetti dalla **casella degli strumenti**. Selezionando e spostando gli elementi nella finestra di progettazione, è possibile comporre visivamente l'interfaccia utente per l'app.

04. Casella degli strumenti

    La casella degli strumenti contiene tutti i controlli che è possibile aggiungere a un modulo. Per aggiungere un controllo al form corrente, fare doppio clic su un controllo o trascinare il controllo.

## <a name="add-controls-to-the-form"></a>Aggiungere controlli al form

Con la finestra di progettazione dei form _Form1_ aperta, utilizzare il riquadro **casella degli strumenti** per aggiungere i controlli seguenti al form:

- Label
- Pulsante
- ListBox
- Casella di testo

È possibile posizionare e ridimensionare i controlli in base alle impostazioni seguenti. Spostarli visivamente in modo che corrispondano allo screenshot seguente oppure fare clic su ogni controllo e configurare le impostazioni nel riquadro **Proprietà** . È anche possibile fare clic sull'area del titolo del modulo per selezionare il modulo:

| Oggetto      | Impostazione  | Valore      |
|-------------|----------|------------|
| **Form**    | Testo     | `Names`    |
|             | Dimensione     | `268, 180` |
|             |          |            |
| **Label**   | Percorso | `12, 9`    |
|             | Testo     | `Names`    |
|             |          |            |
| **ListBox** | Nome     | `lstNames` |
|             | Località | `12, 27`   |
|             | Dimensione     | `120, 94`  |
|             |          |            |
| **Casella di testo** | Nome     | `txtName`  |
|             | Località | `138, 26`  |
|             | Dimensione     | `100, 23`  |
|             |          |            |
| **Button**  | Nome     | `btnAdd`   |
|             | Località | `138, 55`  |
|             | Dimensione     | `100, 23`  |
|             | Testo     | `Add Name` |

Nella finestra di progettazione dovrebbe essere presente un modulo simile al seguente:

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Visual Studio 2019 designer con il modulo aperto per Windows Forms per .NET":::

## <a name="handle-events"></a>Gestire eventi

Ora che il form contiene tutti i controlli disposti, è necessario gestire gli eventi dei controlli per rispondere all'input dell'utente. Con la finestra di progettazione dei form ancora aperta, seguire questa procedura:

01. Selezionare il controllo Button sul form.
01. Nel riquadro **Proprietà** fare clic sull'icona eventi :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: per elencare gli eventi del pulsante.
01. Individuare l'evento **Click** e fare doppio clic su di esso per generare un gestore eventi.

    Questa azione aggiunge il codice seguente al formato:

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    Il codice che verrà inserito in questo gestore aggiungerà il nome specificato dal `txtName` controllo TextBox al `lstNames` controllo ListBox. Tuttavia, si desidera che siano presenti due condizioni per aggiungere il nome: il nome specificato non deve essere vuoto e il nome non deve essere già esistente.

01. Il codice seguente illustra l'aggiunta di un nome al `lstNames` controllo:

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {
        if (!string.IsNullOrWhiteSpace(txtName.Text) && !lstNames.Items.Contains(txtName.Text))
            lstNames.Items.Add(txtName.Text);
    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click
        If Not String.IsNullOrWhiteSpace(txtName.Text) And Not lstNames.Items.Contains(txtName.Text) Then
            lstNames.Items.Add(txtName.Text)
        End If
    End Sub
    ```

## <a name="run-the-app"></a>Eseguire l'app

Ora che l'evento è stato codificato, è possibile eseguire l'app premendo il tasto <kbd>F5</kbd> o selezionando **debug**  >  **Avvia debug** dal menu. Il modulo Visualizza ed è possibile immettere un nome nella casella di testo e quindi aggiungerlo facendo clic sul pulsante.

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="Esecuzione di un Windows Forms per un'app .NET.":::

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Altre informazioni su Windows Forms](../overview/index.md)
