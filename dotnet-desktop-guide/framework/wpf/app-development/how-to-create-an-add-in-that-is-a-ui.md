---
title: "Procedura: creare un componente aggiuntivo che costituisce un'interfaccia utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: fd37e651dc94485becf972533bc095f9ad253335
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966445"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedura: creare un componente aggiuntivo che costituisce un'interfaccia utente

Questo esempio illustra come creare un componente aggiuntivo che è un Windows Presentation Foundation (WPF) ospitato da un'applicazione WPF autonoma.  
  
 Il componente aggiuntivo è un'interfaccia utente che rappresenta un controllo utente WPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione autonoma WPF ospita l'interfaccia utente del componente aggiuntivo come contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio vengono evidenziate le estensioni WPF per il modello di componente aggiuntivo .NET Framework che Abilita questo scenario e si presuppone quanto segue:  
  
- Conoscenza del modello di componente aggiuntivo .NET Framework, tra cui pipeline, componente aggiuntivo e sviluppo host. Se non si ha familiarità con questi concetti, vedere [componenti aggiuntivi ed estensibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione in cui viene illustrata l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere [procedura dettagliata: creazione di un'applicazione estendibile](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Conoscenza delle estensioni WPF per il modello di componente aggiuntivo .NET Framework. Vedere [Cenni preliminari Add-Ins WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  

 Per creare un componente aggiuntivo che è un'interfaccia utente WPF, è necessario codice specifico per ogni segmento di pipeline, per il componente aggiuntivo e per l'applicazione host.  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto

Quando un componente aggiuntivo è un'interfaccia utente, il contratto per il componente aggiuntivo deve implementare <xref:System.AddIn.Contract.INativeHandleContract> . Nell'esempio, `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract> , come illustrato nel codice seguente.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo

Poiché il componente aggiuntivo viene implementato come una sottoclasse del <xref:System.Windows.FrameworkElement> tipo, la visualizzazione del componente aggiuntivo deve anche essere sottoclassata <xref:System.Windows.FrameworkElement> . Nel codice seguente viene illustrata la visualizzazione dei componenti aggiuntivi del contratto, implementata come `WPFAddInView` classe.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
In questo caso, la visualizzazione del componente aggiuntivo è derivata da <xref:System.Windows.Controls.UserControl> . Di conseguenza, l'interfaccia utente del componente aggiuntivo deve anche derivare da <xref:System.Windows.Controls.UserControl> .  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo

Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract> , il componente aggiuntivo è un <xref:System.Windows.FrameworkElement> (come specificato dal segmento della pipeline della visualizzazione del componente aggiuntivo). Pertanto, l'oggetto <xref:System.Windows.FrameworkElement> deve essere convertito in un oggetto <xref:System.AddIn.Contract.INativeHandleContract> prima di attraversare il limite di isolamento. Questa operazione viene eseguita dall'adattatore sul lato del componente aggiuntivo chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> , come illustrato nel codice seguente.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

Nel modello del componente aggiuntivo in cui un componente aggiuntivo restituisce un'interfaccia utente (vedere [creare un Add-In che restituisce un'interfaccia utente](how-to-create-an-add-in-that-returns-a-ui.md)), l'adattatore del componente aggiuntivo ha convertito <xref:System.Windows.FrameworkElement> in un oggetto chiamando <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> . <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> deve essere chiamato anche in questo modello, anche se è necessario implementare un metodo da cui scrivere il codice per chiamarlo. A tale scopo, è necessario eseguire <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> l'override e implementare il codice che chiama <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se il codice che chiama <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> è previsto <xref:System.AddIn.Contract.INativeHandleContract> . In questo caso il chiamante sarà l'adattatore sul lato host, trattato in una sottosezione successiva.  
  
> [!NOTE]
> È anche necessario eseguire l'override di <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> questo modello per abilitare la tabulazione tra l'interfaccia utente dell'applicazione host e l'interfaccia utente del componente aggiuntivo. Per ulteriori informazioni, vedere "limitazioni Add-In WPF" in [wpf Add-Ins Overview](wpf-add-ins-overview.md).  
  
Poiché l'adapter lato componente aggiuntivo implementa un'interfaccia che deriva da <xref:System.AddIn.Contract.INativeHandleContract> , è anche necessario implementare <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A> , sebbene venga ignorato quando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> viene sottoposto a override.  
  
<a name="HostViewPipeline"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host

In questo modello, l'applicazione host in genere prevede che la visualizzazione host sia una <xref:System.Windows.FrameworkElement> sottoclasse. L'adattatore sul lato host deve convertire l'oggetto <xref:System.AddIn.Contract.INativeHandleContract> in un oggetto <xref:System.Windows.FrameworkElement> dopo che <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento. Poiché un metodo non viene chiamato dall'applicazione host per ottenere <xref:System.Windows.FrameworkElement> , la visualizzazione host deve "restituire" la classe che lo <xref:System.Windows.FrameworkElement> contiene. Di conseguenza, la visualizzazione host deve derivare da una sottoclasse di <xref:System.Windows.FrameworkElement> che può contenere altre interfacce utente, ad esempio <xref:System.Windows.Controls.UserControl> . Nel codice seguente viene illustrata la visualizzazione host del contratto, implementata come `WPFAddInHostView` classe.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host

Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract> , l'applicazione host prevede un <xref:System.Windows.Controls.UserControl> (come specificato dalla visualizzazione host). Di conseguenza, l'oggetto <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un oggetto <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento, prima di essere impostato come contenuto della visualizzazione host, che deriva da <xref:System.Windows.Controls.UserControl> .  
  
La conversione viene eseguita dall'adattatore sul lato host, come illustrato nel codice seguente.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Come si può notare, l'adapter sul lato host acquisisce chiamando <xref:System.AddIn.Contract.INativeHandleContract> il metodo dell'adattatore sul lato del componente aggiuntivo, ovvero <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> il punto in cui il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento.  
  
L'adapter sul lato host converte quindi <xref:System.AddIn.Contract.INativeHandleContract> in un oggetto <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> . Infine, <xref:System.Windows.FrameworkElement> viene impostato come contenuto della visualizzazione host.  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo

Una volta creati l'adattatore sul lato del componente aggiuntivo e la visualizzazione componente aggiuntivo, il componente aggiuntivo può essere implementato mediante derivazione dalla visualizzazione componente aggiuntivo, come illustrato nel codice seguente.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

Da questo esempio è possibile vedere un vantaggio interessante di questo modello: gli sviluppatori di componenti aggiuntivi devono solo implementare il componente aggiuntivo (poiché si tratta dell'interfaccia utente), anziché una classe del componente aggiuntivo e un'interfaccia utente del componente aggiuntivo.  
  
<a name="HostApp"></a>

## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host

Con l'adapter sul lato host e la visualizzazione host creati, l'applicazione host può utilizzare il .NET Framework modello di componente aggiuntivo per aprire la pipeline e acquisire una visualizzazione host del componente aggiuntivo. Il codice riportato di seguito illustra i diversi passaggi.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

L'applicazione host usa il tipico codice del modello di componente aggiuntivo .NET Framework per attivare il componente aggiuntivo, che restituisce in modo implicito la visualizzazione host all'applicazione host. L'applicazione host Visualizza successivamente la visualizzazione host, ovvero un oggetto <xref:System.Windows.Controls.UserControl> , da un oggetto <xref:System.Windows.Controls.Grid> .  
  
 Il codice per l'elaborazione delle interazioni con l'interfaccia utente del componente aggiuntivo viene eseguito nel dominio dell'applicazione del componente aggiuntivo. Di seguito vengono riportati alcuni esempi di interazione:  
  
- Gestione dell' <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
- Visualizzazione di <xref:System.Windows.MessageBox> .  
  
 Questa attività è completamente isolata dall'applicazione host.  
  
## <a name="see-also"></a>Vedere anche

- [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md)
