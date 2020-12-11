---
title: Informazioni Windows Forms
description: Questo articolo fornisce una panoramica delle Windows Forms con .NET Core e .NET 5.
ms.date: 10/26/2020
ms.topic: overview
ms.openlocfilehash: a0908891d9391d5820fe75cac69278ddda1b2244
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966010"
---
# <a name="desktop-guide-windows-forms-net"></a>Guida al desktop (Windows Forms .NET)

Benvenuti nella Guida al desktop per Windows Forms, un Framework dell'interfaccia utente che crea applicazioni client desktop complete per Windows. La piattaforma di sviluppo Windows Forms supporta un'ampia gamma di funzionalità di sviluppo di app, tra cui controlli, elementi grafici, data binding e input dell'utente. Windows Forms offre una finestra di progettazione visiva con trascinamento della selezione in Visual Studio per creare con facilità Windows Forms app.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Esistono due implementazioni di Windows Forms:

01. Implementazione open source ospitata in [GitHub](https://github.com/dotnet/winforms).

    Questa versione viene eseguita in .NET 5 e .NET Core 3,1. La finestra di progettazione visiva Windows Forms richiede almeno [Visual Studio 2019 versione 16,8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms).

01. Implementazione di .NET Framework 4 supportata da Visual Studio 2019 e Visual Studio 2017.

    .NET Framework 4 è una versione di .NET solo Windows ed è considerato un componente del sistema operativo Windows. Questa versione di Windows Forms viene distribuita con .NET Framework.

Questa guida per i desktop è scritta per Windows Forms in .NET 5. Per ulteriori informazioni sulla versione .NET Framework di Windows Forms, vedere [Windows Forms per .NET Framework](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true).

## <a name="introduction"></a>Introduzione

Windows Forms è un Framework dell'interfaccia utente per la creazione di applicazioni desktop di Windows. Offre uno dei modi più produttivi per creare app desktop basate sulla finestra di progettazione visiva fornita in Visual Studio. Funzionalità come il posizionamento con trascinamento della selezione di controlli visivi semplifica la creazione di applicazioni desktop.

Con Windows Forms, si sviluppano app graficamente complesse e facili da distribuire, aggiornare e lavorare in modalità offline o connessa a Internet. Windows Forms app possono accedere all'hardware locale e file system del computer in cui è in esecuzione l'app.

Per informazioni su come creare un'app Windows Forms, vedere [esercitazione: creare una nuova app WinForms (Windows Forms .NET)](../get-started/create-app-visual-studio.md).

## <a name="why-migrate-from-net-framework"></a>Vantaggi della migrazione da .NET Framework

Windows Forms per .NET 5,0 fornisce nuove funzionalità e miglioramenti rispetto a .NET Framework. Per ulteriori informazioni, vedere Novità [di Windows Forms per .NET 5](../whats-new/index.md). Per informazioni su come eseguire la migrazione di un'app, vedere [come eseguire la migrazione di un'app desktop Windows Forms a .NET 5](../migration/index.md).

## <a name="build-rich-interactive-user-interfaces"></a>Crea interfacce utente avanzate e interattive

Windows Forms è una tecnologia dell'interfaccia utente per .NET, un set di librerie gestite che semplificano le attività comuni delle app, ad esempio la lettura e la scrittura nel file system. Quando si usa un ambiente di sviluppo come Visual Studio, è possibile creare Windows Forms app Smart client che visualizzano informazioni, richiedono l'input dagli utenti e comunicano con computer remoti tramite una rete.

In Windows Forms un *modulo* è una superficie visiva sulla quale è possibile visualizzare informazioni per l'utente. In genere si compilano Windows Forms app mediante l'aggiunta di controlli ai moduli e lo sviluppo di risposte alle azioni dell'utente, ad esempio clic del mouse o pressioni dei tasti. Un *controllo* è un elemento discreto dell'interfaccia utente che Visualizza i dati o accetta input di dati.

Quando un utente esegue un'azione nel form o in uno dei controlli, viene generato un evento. L'app reagisce a questi eventi con il codice ed elabora gli eventi quando si verificano.<!-- TODO  For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md).-->

Windows Forms contiene un'ampia gamma di controlli che è possibile aggiungere ai form: controlli che visualizzano caselle di testo, pulsanti, caselle di riepilogo a discesa, pulsanti di opzione e persino pagine Web.<!-- TODO For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).--> Se un controllo esistente non soddisfa le esigenze, Windows Forms supporta anche la creazione di controlli personalizzati usando la <xref:System.Windows.Forms.UserControl> classe.

Windows Forms dispone di controlli dell'interfaccia utente avanzati che emulano le funzionalità nelle app di fascia alta, come Microsoft Office. Quando si usano i <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> controlli e, è possibile creare barre degli strumenti e menu contenenti testo e immagini, visualizzare sottomenu e ospitare altri controlli, ad esempio caselle di testo e caselle combinate.

Con il trascinamento della selezione **Progettazione Windows Form** in Visual Studio, è possibile creare facilmente Windows Forms app. È sufficiente selezionare i controlli con il cursore e posizionarli nel punto desiderato del form. Per facilitare l'allineamento dei controlli, nella finestra di progettazione vengono forniti strumenti quali linee della griglia e guide di allineamento. È possibile utilizzare i <xref:System.Windows.Forms.FlowLayoutPanel> <xref:System.Windows.Forms.TableLayoutPanel> controlli, e <xref:System.Windows.Forms.SplitContainer> per creare layout di form avanzati in meno tempo.

Infine, se è necessario creare elementi dell'interfaccia utente personalizzati, lo spazio dei nomi <xref:System.Drawing> contiene diverse classi che consentono di creare linee, cerchi e altre forme direttamente in un form.

### <a name="create-forms-and-controls"></a>Creazione di form e controlli

Per informazioni dettagliate sull'uso di queste funzionalità, vedere i seguenti argomenti della Guida.

- [Come aggiungere un modulo a un progetto](../forms/how-to-add.md)
- [Come aggiungere controlli a un form](../controls/how-to-add-to-a-form.md)

<!-- TODO
| Using the <xref:System.Windows.Forms.ToolStrip> Control | [How to: Create a Basic ToolStrip with Standard Items Using the Designer](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md) |
| Creating graphics with <xref:System.Drawing> | [Getting Started with Graphics Programming](./advanced/getting-started-with-graphics-programming.md)  |
| Creating custom controls                     | [How to: Inherit from the UserControl Class](./controls/how-to-inherit-from-the-usercontrol-class.md) |
-->

## <a name="display-and-manipulate-data"></a>Visualizzare e modificare i dati

Molte app devono visualizzare i dati da un database, da un file XML o JSON, da un servizio Web o da un'altra origine dati. In Windows Form viene fornito un controllo denominato <xref:System.Windows.Forms.DataGridView> che consente di visualizzare dati tabulari in un formato tradizionale basato su righe e colonne, in modo che ciascun blocco di dati occupi una singola cella. Usando <xref:System.Windows.Forms.DataGridView> è possibile personalizzare l'aspetto delle singole celle, bloccare righe e colonne arbitrarie nonché visualizzare controlli complessi all'interno delle celle.

La connessione alle origini dati tramite una rete è un'attività semplice con Windows Forms. Il <xref:System.Windows.Forms.BindingSource> componente rappresenta una connessione a un'origine dati ed espone metodi per l'associazione dei dati ai controlli, lo spostamento ai record precedenti e successivi, la modifica di record e il salvataggio delle modifiche nell'origine originale. Il controllo <xref:System.Windows.Forms.BindingNavigator> fornisce un'interfaccia semplice tramite il componente <xref:System.Windows.Forms.BindingSource> per gli utenti per spostarsi tra i record.

È possibile creare facilmente controlli con associazione a dati usando la finestra Origini dati in Visual Studio. Nella finestra vengono visualizzate origini dati quali database, servizi Web e oggetti nel progetto. È possibile creare controlli associati a dati mediante il trascinamento di elementi da questa finestra nei form del progetto. È anche possibile connettere i controlli esistenti ai dati mediante il trascinamento di oggetti dalla finestra Origini dati nei controlli esistenti.

Un altro tipo di data binding che è possibile gestire in Windows Forms sono le *impostazioni*. La maggior parte delle app deve conservare alcune informazioni sullo stato di run-time, ad esempio le ultime dimensioni note dei form, e conservare i dati relativi alle preferenze dell'utente, ad esempio i percorsi predefiniti per i file salvati. La funzionalità Impostazioni applicazione risolve queste problematiche offrendo un modo semplice per archiviare entrambi i tipi di impostazioni sul computer client. Dopo aver definito queste impostazioni usando Visual Studio o un editor di codice, le impostazioni vengono rese permanente come XML e rilette automaticamente in memoria in fase di esecuzione.

<!-- TODO
### Display and manipulate data

For step-by-step information about how to use these features, see the following Help topics.

| Description                                                   | Help topic                                                                                                                                                        |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Using the <xref:System.Windows.Forms.BindingSource> component | [How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer](./controls/bind-wf-controls-with-the-bindingsource.md)                  |
| Working with ADO.NET data sources                             | [How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md) |
| Using the Data Sources window                                 | [Bind Windows Forms controls to data in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)                             |
| Using app settings                                            | [How to: Create Application Settings](./advanced/how-to-create-application-settings.md)                                                                           |

-->

## <a name="deploy-apps-to-client-computers"></a>Distribuire le app nei computer client

Dopo aver scritto l'app, è necessario inviare l'app agli utenti in modo che possano installarla ed eseguirla sui propri computer client. Quando si usa la tecnologia ClickOnce, è possibile distribuire le app da Visual Studio con pochi clic e fornire agli utenti un URL che punta all'app sul Web. ClickOnce gestisce tutti gli elementi e le dipendenze nell'app e garantisce che l'app sia installata correttamente nel computer client.

Le app ClickOnce possono essere configurate per essere eseguite solo quando l'utente è connesso alla rete oppure per l'esecuzione sia online che offline. Quando si specifica che un'app deve supportare l'operazione offline, ClickOnce aggiunge un collegamento all'app nel menu **Start** dell'utente. L'utente può quindi aprire l'app senza usare l'URL.

Quando si aggiorna l'app, si pubblica un nuovo manifesto di distribuzione e una nuova copia dell'app sul server Web. ClickOnce rileverà che è disponibile un aggiornamento e aggiornerà l'installazione dell'utente. Per aggiornare le app precedenti non è necessaria alcuna programmazione personalizzata.

<!-- TODO

### Deploy ClickOnce apps

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about how to use these features, see the following Help topics,

|Description|Help topic|
|-----------------|----------------|
|Deploying an app by using ClickOnce|[How to: Publish a ClickOnce Application using the Publish Wizard](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Walkthrough: Manually Deploying a ClickOnce Application](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Updating a ClickOnce deployment|[How to: Manage Updates for a ClickOnce Application](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Managing security with ClickOnce|[How to: Enable ClickOnce Security Settings](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|
-->

<!-- TODO
## Other controls and features

There are many other features in Windows Forms that make implementing common tasks fast and easy, such as support for creating dialog boxes, printing, adding help and documentation, and localizing your app to multiple languages.

### Implement other controls and features

For step-by-step information about how to use these features, see the following Help topics.

| Description | Help topic |
|-------------|------------|
|Printing the contents of a form | [How to: Print Graphics in Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [How to: Print a Multi-Page Text File in Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md) |
|Learn more about Windows Forms security | [Security in Windows Forms Overview](security-in-windows-forms-overview.md) |
-->

## <a name="see-also"></a>Vedere anche

- [Esercitazione: creare una nuova app WinForms (Windows Forms .NET)](../get-started/create-app-visual-studio.md)
- [Come aggiungere un modulo a un progetto (Windows Forms .NET)](../forms/how-to-add.md)
- [Aggiungere un controllo (Windows Forms .NET)](../controls/how-to-add-to-a-form.md)
