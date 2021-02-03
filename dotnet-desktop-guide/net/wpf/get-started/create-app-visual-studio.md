---
title: Esercitazione su come creare una nuova app con Visual Studio
description: Seguire questa esercitazione per informazioni su come creare una nuova app WPF per .NET con Visual Studio 2019.
ms.date: 01/18/2021
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: c8a705b35bdd5193accf124deb67c24b2d02bb70
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506872"
---
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a>Esercitazione: creare una nuova applicazione WPF (WPF .NET)

In questa breve esercitazione si apprenderà come creare una nuova app Windows Presentation Foundation (WPF) con Visual Studio. Una volta generata l'app iniziale, si apprenderà come aggiungere controlli e come gestire gli eventi. Al termine di questa esercitazione, si disporrà di una semplice app che aggiunge nomi a una casella di riepilogo.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> - Creare una nuova app WPF
> - Aggiungere controlli a un form
> - Gestire gli eventi di controllo per fornire la funzionalità dell'app
> - Eseguire l'app

Ecco un'anteprima dell'app che verrà creata durante l'esercitazione seguente:

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="Esercitazione sull'app di esempio per WPF completata":::

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,9 o versioni successive](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - Selezionare il [carico di lavoro di Visual Studio Desktop](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)
  - Selezionare il [singolo componente .NET 5](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)

## <a name="create-a-wpf-app"></a>Creare un'app WPF

Il primo passaggio per creare una nuova app è l'apertura di Visual Studio e la generazione dell'app da un modello.

01. Aprire Visual Studio.
01. Selezionare **Crea un nuovo progetto**.

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Creare un nuovo progetto WPF in Visual Studio 2019 per .NET":::

01. Nella casella **Cerca modelli** Digitare **WPF**, quindi premere <kbd>invio</kbd>.
01. Nell'elenco a discesa **linguaggio codice** scegliere **C#** o **Visual Basic**.
01. Nell'elenco modelli selezionare **applicazione WPF** e quindi fare clic su **Avanti**.

    > [!IMPORTANT]
    > Non selezionare il modello **applicazione WPF (.NET _Framework_)** .

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="Cercare il modello WPF in Visual Studio 2019 per .NET":::

01. Nella finestra **Configura nuovo progetto** eseguire le operazioni seguenti:

    01. Nella casella **nome progetto** immettere **i nomi**.
    01. Selezionare la casella **di controllo posiziona soluzione e progetto nella stessa directory** .
    01. Facoltativamente, scegliere un **percorso** diverso per salvare il codice.
    01. Selezionare il pulsante **Avanti**.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="Configurare il nuovo progetto WPF in Visual Studio 2019 per .NET":::

01. Nella finestra **informazioni aggiuntive** selezionare **.NET 5,0 (corrente)** per Framework di **destinazione** e verificare che la casella di controllo **Esegui su .NET Framework** sia deselezionata. Selezionare il pulsante **Crea**.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Selezionare il Framework di destinazione per il nuovo progetto WPF in Visual Studio 2019 per .NET":::

Una volta generata l'app, Visual Studio dovrebbe aprire il riquadro finestra di progettazione XAML per la finestra predefinita, _MainWindow_. Se la finestra di progettazione non è visibile, fare doppio clic sul file _MainWindow. XAML_ nel riquadro **Esplora soluzioni** per aprire la finestra di progettazione.

### <a name="important-parts-of-visual-studio"></a>Parti importanti di Visual Studio

Il supporto per WPF in Visual Studio include cinque componenti importanti con cui si interagirà quando si crea un'app:

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="I componenti importanti di Visual Studio da tenere presente durante la creazione di un progetto WPF per .NET":::

01. Esplora soluzioni

    Tutti i file di progetto, il codice, le finestre e le risorse verranno visualizzati in questo riquadro.

02. Proprietà

    Questo riquadro Mostra le impostazioni delle proprietà che è possibile configurare in base all'elemento selezionato. Se, ad esempio, si seleziona un elemento da **Esplora soluzioni**, verranno visualizzate le impostazioni delle proprietà correlate al file. Se si seleziona un oggetto nella **finestra di progettazione**, verranno visualizzate le impostazioni per tale elemento.

03. Casella degli strumenti

    La casella degli strumenti contiene tutti i controlli che è possibile aggiungere a un modulo. Per aggiungere un controllo al form corrente, fare doppio clic su un controllo o trascinare il controllo.

04. Finestra di progettazione XAML

    Si tratta della finestra di progettazione per un documento XAML. È interattivo ed è possibile trascinare gli oggetti dalla **casella degli strumenti**. Selezionando e spostando gli elementi nella finestra di progettazione, è possibile comporre visivamente l'interfaccia utente per l'app.

    Quando sia la finestra di progettazione che l'editor sono visibili, le modifiche apportate a una vengono riflesse nell'altra. Quando si selezionano gli elementi nella finestra di progettazione, nel riquadro **Proprietà** vengono visualizzate le proprietà e gli attributi relativi a tale oggetto.

05. Editor di codice XAML

    Si tratta dell'editor di codice XAML per un documento XAML. L'editor di codice XAML è un modo per creare manualmente l'interfaccia utente senza una finestra di progettazione. La finestra di progettazione può dedurre i valori delle proprietà di un controllo quando il controllo viene aggiunto nella finestra di progettazione. L'editor di codice XAML offre un maggiore controllo.

    Quando sia la finestra di progettazione che l'editor sono visibili, le modifiche apportate a una vengono riflesse nell'altra. Quando si sposta il cursore del testo nell'editor di codice, nel riquadro **Proprietà** vengono visualizzate le proprietà e gli attributi relativi a tale oggetto.

## <a name="examine-the-xaml"></a>Esaminare il codice XAML

Quando il progetto viene aperto, l'editor di codice XAML è visibile con una quantità minima di codice XAML per visualizzare la finestra:

```xaml
<Window x:Class="Names.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Names"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>

    </Grid>
</Window>
```

Analizziamo questo codice XAML per comprenderlo meglio. XAML è semplicemente XML che può essere elaborato dai compilatori usati da WPF. Descrive l'interfaccia utente di WPF e interagisce con il codice .NET. Per comprendere il codice XAML, è necessario avere almeno familiarità con le nozioni di base di XML.

La radice del documento `<Window>` rappresenta il tipo di oggetto descritto dal file XAML. Sono stati dichiarati otto attributi e in genere appartengono a tre categorie:

- Spazi dei nomi

  Uno spazio dei nomi XML fornisce la struttura al codice XML, determinando che cosa è o non può essere dichiarato nel file.

  L' `xmlns` attributo Main importa lo spazio dei nomi XML per l'intero file e, in questo caso, esegue il mapping ai tipi dichiarati da WPF. Gli altri spazi dei nomi XML dichiarano un prefisso e importano altri tipi e oggetti per il file XAML. Ad esempio, lo `xmlns:local` spazio dei nomi dichiara il `local` prefisso ed esegue il mapping agli oggetti dichiarati dal progetto, quelli dichiarati nello `Names` spazio dei nomi del codice.

- Attributo `x:Class`

  Questo attributo esegue il mapping `<Window>` di al tipo definito dal codice: il file _MainWindow.XAML.cs_ o _MainWindow. XAML. vb_ , che è la `Names.MainWindow` classe.

- Attributo `Title`

  Qualsiasi attributo normale dichiarato nell'oggetto XAML imposta una proprietà di tale oggetto. In questo caso l' `Title` attributo imposta la `Window.Title` Proprietà.

## <a name="change-the-window"></a>Modificare la finestra

Prima di tutto, eseguiamo il progetto e visualizziamo l'output predefinito. Si noterà che viene visualizzata una finestra, senza controlli, e un titolo **MainWindow**:

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="App WPF vuota":::

Per l'app di esempio, questa finestra è troppo grande e la barra del titolo non è descrittiva. Modificare il titolo e le dimensioni della finestra modificando gli attributi appropriati in XAML con i valori seguenti:

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a>Preparare il layout

WPF fornisce un sistema di layout potente con molti controlli di layout diversi. I controlli di layout consentono di posizionare e ridimensionare i controlli figlio e possono anche eseguire tale operazione automaticamente. Il controllo di layout predefinito fornito in questo codice XAML è il `<Grid>` controllo.

Il `Grid` controllo consente di definire le righe e le colonne, in modo analogo a una tabella, e di posizionare i controlli all'interno dei limiti di una combinazione di riga e colonna specifica. È possibile aggiungere un numero qualsiasi di controlli figlio o altri controlli di layout a `Grid` . Ad esempio, è possibile inserire un altro `Grid` controllo in una combinazione di riga e colonna specifica e il nuovo oggetto `Grid` può quindi definire più righe e colonne e avere i propri elementi figlio.

Il `<Grid>` controllo definisce le righe e le colonne in cui saranno presenti i controlli. In una griglia è sempre presente una sola riga e colonna dichiarata, ovvero la griglia per impostazione predefinita è una singola cella. Questo non offre una maggiore flessibilità per l'inserimento di controlli.

Prima di aggiungere le nuove righe e colonne, aggiungere un nuovo attributo all' `<Grid>` elemento: `Margin="10"` . Questa operazione consente di ingrandire la griglia dalla finestra e renderla leggermente più gradevole.

Definire quindi due righe e due colonne, dividendo la griglia in quattro celle:

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

Selezionare la griglia nell'editor del codice XAML o nella finestra di progettazione XAML. si noterà che la finestra di progettazione XAML mostra ogni riga e colonna:

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="Un'app WPF con il margine impostato in una griglia":::

## <a name="add-the-first-control"></a>Aggiungere il primo controllo

Ora che la griglia è stata creata, è possibile iniziare ad aggiungere controlli. Innanzitutto, iniziare con il controllo Label. Creare un nuovo `<Label>` elemento all'interno dell' `<Grid>` elemento, dopo le definizioni di riga e colonna, e assegnare un valore stringa `Names` :

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

`<Label>Names</Label>`Definisce il contenuto `Names` . Alcuni controlli comprendono come gestire il contenuto, altri no. Il contenuto di un controllo viene mappato alla `Content` Proprietà. Impostando il contenuto tramite la sintassi dell'attributo XAML, usare il formato seguente: `<Label Content="Names" />` . Entrambe le modalità consentono di ottenere la stessa operazione, impostando il contenuto dell'etichetta in modo da visualizzare il testo `Names` .

Si è verificato un problema, ma l'etichetta occupa metà della finestra perché è stata assegnata automaticamente alla prima riga e alla colonna della griglia. Per la prima riga, non è necessario molto spazio perché verrà usata solo tale riga per l'etichetta. Modificare l' `Height` attributo del primo `<RowDefinition>` da `*` a `Auto` . Il `Auto` valore Ridimensiona automaticamente la riga della griglia alla dimensione del contenuto, in questo caso il controllo Label.

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

Si noti che la finestra di progettazione Mostra ora l'etichetta che occupa una piccola quantità dell'altezza disponibile. È ora disponibile più spazio per la riga successiva da occupare. La maggior parte dei controlli definisce un tipo di altezza e di larghezza che devono occupare più a loro aspetto. Nel caso del controllo Label, ha un valore di altezza che garantisce che sia possibile leggerlo.

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="Un'app WPF con il margine impostato in una griglia e un controllo etichetta nella prima riga":::

### <a name="control-placement"></a>Posizionamento del controllo

Si esaminerà il posizionamento del controllo. L'etichetta creata nella sezione precedente è stata inserita automaticamente nella riga 0 e nella colonna 0 della griglia. Il numero di righe e colonne inizia da 0 e viene incrementato di 1 per ogni nuova riga o colonna. Il controllo non conosce nulla sulla griglia e il controllo non definisce alcuna proprietà per controllarne la posizione all'interno della griglia. Il controllo potrebbe essere stato inserito anche in un altro controllo di layout che ha un proprio set di regole che definiscono il modo in cui posizionare i controlli.

Come si indica a un controllo di usare una riga o una colonna diversa quando il controllo non è a conoscenza della griglia? Proprietà associate. La griglia sfrutta il potente sistema di proprietà fornito da WPF. La griglia definisce le nuove proprietà che i controlli figlio possono dichiarare e utilizzare. Le proprietà non sono effettivamente presenti nel controllo stesso, sono collegate dalla griglia quando il controllo viene aggiunto alla griglia.

La griglia definisce due proprietà per determinare la posizione di riga e colonna di un controllo figlio: `Grid.Row` e `Grid.Column` . Se queste proprietà vengono omesse dal controllo, è implicito che abbiano i valori predefiniti 0, quindi il controllo viene inserito in riga `0` e colonna `0` della griglia. Provare a modificare la posizione del `<Label>` controllo impostando l' `Grid.Column` attributo su `1` :

```xaml
<Label Grid.Column="1">Names</Label>
```

Si noti che l'etichetta ora è stata spostata nella seconda colonna. È possibile usare le `Grid.Row` `Grid.Column` proprietà associate e per inserire i controlli successivi che verranno creati. Per il momento, tuttavia, ripristinare l'etichetta sulla riga 0.

## <a name="create-the-name-list-box"></a>Creazione della casella di riepilogo nome

Ora che la griglia è dimensionata correttamente e l'etichetta è stata creata, aggiungere un controllo casella di riepilogo sulla riga sotto l'etichetta. La casella di riepilogo si troverà in righe `1` e colonne `0` . Verrà inoltre fornito a questo controllo il nome di `lstNames` . Una volta denominato, il controllo può essere usato come riferimento nel code-behind. Il nome viene assegnato al controllo con l' `x:Name` attributo.

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a>Aggiungere i controlli rimanenti

Gli ultimi due controlli da aggiungere sono una casella di testo e un pulsante, che verranno usati dall'utente per immettere un nome da aggiungere alla casella di riepilogo. Tuttavia, anziché tentare di creare più righe e colonne per la griglia, questi controlli vengono inseriti nel `<StackPanel>` controllo del layout.

Il pannello dello stack è diverso dalla griglia in cui vengono posizionati i controlli. Quando si indica alla griglia dove si desidera che i controlli siano con le `Grid.Row` `Grid.Column` proprietà e associate, il pannello dello stack funziona automaticamente inserendo il primo controllo, quindi inserendo il controllo successivo, continuando fino a quando tutti i controlli non sono stati inseriti. "Impila" ogni controllo sotto l'altro.

Creare il `<StackPanel>` controllo dopo la casella di riepilogo e inserirlo nella colonna riga della griglia `1` `1` . Aggiungere un altro attributo denominato `Margin` con un valore `5,0,0,0` :

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

L' `Margin` attributo è stato usato in precedenza nella griglia, ma è stato inserito un solo valore, `10` . A questo punto è stato usato il valore `5,0,0,0` nel pannello stack. Il margine è un `Thickness` tipo e può interpretare entrambi i valori. Uno spessore definisce lo spazio intorno a ogni lato di un frame rettangolare, a **sinistra**, in **alto**, a **destra**, in **basso**, rispettivamente. Se il valore per il margine è un singolo valore, questo valore viene utilizzato per tutti e quattro i lati.

Successivamente, creare un `<TextBox>` `<Button>` controllo e in `<StackPanel>` .

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

Il layout per la finestra è completo. Tuttavia, l'app non dispone di alcuna logica per essere effettivamente funzionante. Successivamente, è necessario associare gli eventi di controllo al codice e far sì che l'app esegua effettivamente un'operazione.

## <a name="add-code-for-the-click-event"></a>Aggiungere il codice per l'evento click

Il `<Button>` creato ha un `Click` evento che viene generato quando l'utente preme il pulsante. È possibile sottoscrivere questo evento e aggiungere il codice per aggiungere un nome alla casella di riepilogo. Così come si imposta una proprietà su un controllo aggiungendo un attributo XAML, è possibile usare un attributo XAML per sottoscrivere un evento. Impostare l' `Click` attributo su `ButtonAddName_Click`

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

A questo punto è necessario generare il codice del gestore. Fare clic con il pulsante destro del mouse su `ButtonAddName_Click` e scegliere **Vai a definizione**. Verrà generato un metodo nel code-behind che corrisponde al nome del gestore immesso.

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

Aggiungere quindi il codice seguente per eseguire questi tre passaggi:

01. Assicurarsi che la casella di testo contenga un nome.
01. Verificare che il nome immesso nella casella di testo non esista già.
01. Aggiungere il nome alla casella di riepilogo.

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a>Eseguire l'app

Ora che l'evento è stato codificato, è possibile eseguire l'app premendo il tasto <kbd>F5</kbd> o selezionando **debug**  >  **Avvia debug** dal menu. Viene visualizzata la finestra ed è possibile immettere un nome nella casella di testo e quindi aggiungerlo facendo clic sul pulsante.

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="Esecuzione di un Windows Presentation Foundation (WPF) per un'app .NET.":::

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Altre informazioni su Windows Presentation Foundation](../overview/index.md)
