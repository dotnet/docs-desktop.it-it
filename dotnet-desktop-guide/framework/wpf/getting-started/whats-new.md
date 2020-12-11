---
title: Novità di WPF versione 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: e6511e298201202c9f2917af8bcf5f3832dd0149
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951594"
---
# <a name="whats-new-in-wpf-version-45"></a>Novità di WPF versione 4.5
<a name="introduction"></a> Questo argomento contiene informazioni sulle funzionalità nuove e migliorate della [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] versione 4,5.  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Controllo della barra multifunzione](#ribbon_control)  
  
- [Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati](#grouped_virtualization)  
  
- [Nuove funzionalità per il VirtualizingPanel](#VirtualizingPanel)  
  
- [Associazione alle proprietà statiche](#static_properties)  
  
- [Accesso alle raccolte su thread non di interfaccia utente](#xthread_access)  
  
- [Convalida dei dati in modo sincrono e asincrono](#INotifyDataErrorInfo)  
  
- [Aggiornamento automatico dell'origine di un data binding](#delay)  
  
- [Associazione a tipi che implementano ICustomTypeProvider](#ICustomTypeProvider)  
  
- [Recupero delle informazioni del data binding da un'espressione di associazione](#binding_state)  
  
- [Verifica di un oggetto DataContext valido](#DisconnectedSource)  
  
- [Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)](#live_shaping)  
  
- [Supporto migliorato per stabilire un riferimento debole a un evento](#weak_event_pattern)  
  
- [Nuovi metodi per la classe Dispatcher](#async)  
  
- [Estensioni di markup per gli eventi](#events_markup_extenions)  
  
<a name="ribbon_control"></a>
## <a name="ribbon-control"></a>Controllo della barra multifunzione  
 WPF 4,5 viene fornito con un <xref:System.Windows.Controls.Ribbon.Ribbon> controllo che ospita una barra di accesso rapido, il menu dell'applicazione e le schede.  Per altre informazioni, vedere [Cenni preliminari sulla barra multifunzione](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati  
 La virtualizzazione dell'interfaccia utente viene eseguita quando si genera un subset di elementi dell'interfaccia utente da un numero maggiore di elementi dati visibili sullo schermo. <xref:System.Windows.Controls.VirtualizingPanel>Definisce la <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> proprietà associata che consente la virtualizzazione dell'interfaccia utente per i dati raggruppati.  Per ulteriori informazioni sul raggruppamento dei dati, vedere Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML.  Per ulteriori informazioni sulla virtualizzazione dei dati raggruppati, vedere la <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> proprietà associata.  
  
<a name="VirtualizingPanel"></a>
## <a name="new-features-for-the-virtualizingpanel"></a>Nuove funzionalità per il VirtualizingPanel  
  
1. È possibile specificare se un oggetto <xref:System.Windows.Controls.VirtualizingPanel> , ad esempio <xref:System.Windows.Controls.VirtualizingStackPanel> , Visualizza elementi parziali utilizzando la <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> proprietà associata. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è impostato su <xref:System.Windows.Controls.ScrollUnit.Item> , in <xref:System.Windows.Controls.VirtualizingPanel> verranno visualizzati solo gli elementi completamente visibili. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è impostato su <xref:System.Windows.Controls.ScrollUnit.Pixel> , <xref:System.Windows.Controls.VirtualizingPanel> può visualizzare elementi parzialmente visibili.  
  
2. È possibile specificare le dimensioni della cache prima e dopo il riquadro di visualizzazione quando l'oggetto esegue la <xref:System.Windows.Controls.VirtualizingPanel> virtualizzazione utilizzando la <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> proprietà associata.  La cache è la quantità di spazio sopra o sotto il viewport in cui gli elementi non sono virtualizzati.  È possibile migliorare le prestazioni usando una cache per evitare che vengano generati elementi dell'interfaccia utente quando ne viene eseguito lo scorrimento nella visualizzazione. La cache viene popolata con una priorità inferiore in modo che l'applicazione rimanga reattiva durante l'operazione. La <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> proprietà determina l'unità di misura utilizzata da <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType> .  
  
<a name="static_properties"></a>
## <a name="binding-to-static-properties"></a>Associazione alle proprietà statiche  
 È possibile utilizzare proprietà statiche come origine di un data binding. Il motore di data binding riconosce quando cambia il valore della proprietà, se viene generato un evento statico.  Ad esempio, se la classe `SomeClass` definisce una proprietà statica denominata `MyProperty`, `SomeClass` può definire un evento statico generato quando cambia il valore di `MyProperty`.  L'evento statico può utilizzare una delle firme seguenti.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Si noti che nel primo caso, la classe espone un evento statico denominato *PropertyName* `Changed` che passa <xref:System.EventArgs> al gestore eventi.  Nel secondo caso, la classe espone un evento statico denominato `StaticPropertyChanged` che passa <xref:System.ComponentModel.PropertyChangedEventArgs> al gestore eventi. Una classe che implementa la proprietà statica può scegliere di generare notifiche delle modifiche delle proprietà utilizzando uno dei metodi.  
  
<a name="xthread_access"></a>
## <a name="accessing-collections-on-non-ui-threads"></a>Accesso alle raccolte su thread non di interfaccia utente  
 WPF permette di accedere e modificare le raccolte di dati su thread diversi da quello che ha creato la raccolta.  In questo modo è possibile utilizzare un thread in background per ricevere dati da un'origine esterna, ad esempio un database, e visualizzare i dati sul thread dell'interfaccia utente.  Utilizzando un altro thread per modificare la raccolta, l'interfaccia utente rimane reattiva all'interazione dell'utente.  
  
<a name="INotifyDataErrorInfo"></a>
## <a name="synchronously-and-asynchronously-validating-data"></a>Convalida dei dati in modo sincrono e asincrono  
 L' <xref:System.ComponentModel.INotifyDataErrorInfo> interfaccia consente alle classi di entità dati di implementare regole di convalida personalizzate ed esporre i risultati della convalida in modo asincrono. Questa interfaccia supporta anche gli oggetti di errori personalizzati, più errori per ogni proprietà, gli errori tra le proprietà e gli errori a livello di entità.  Per altre informazioni, vedere <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Aggiornamento automatico dell'origine di un data binding  
 Se si usa un data binding per aggiornare un'origine dati, è possibile usare la <xref:System.Windows.Data.BindingBase.Delay%2A> proprietà per specificare un intervallo di tempo dopo la modifica della proprietà nella destinazione prima dell'aggiornamento dell'origine.  Si supponga, ad esempio, di disporre di un oggetto con i <xref:System.Windows.Controls.Slider> <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> dati di proprietà bidirezionali associati a una proprietà di un oggetto dati e che la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà sia impostata su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .  In questo esempio, quando l'utente sposta l'oggetto <xref:System.Windows.Controls.Slider> , l'origine viene aggiornata per ogni pixel che lo <xref:System.Windows.Controls.Slider> Sposta.  L'oggetto di origine richiede in genere il valore del dispositivo di scorrimento solo quando il dispositivo di scorrimento <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> smette di cambiare.  Per evitare che l'aggiornamento dell'origine sia troppo frequente, utilizzare <xref:System.Windows.Data.BindingBase.Delay%2A> per specificare che l'origine non deve essere aggiornata fino a quando il cursore smette di essere spostato.  
  
<a name="ICustomTypeProvider"></a>
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Associazione a tipi che implementano ICustomTypeProvider  
 WPF supporta data binding a oggetti che implementano <xref:System.Reflection.ICustomTypeProvider> , noti anche come tipi personalizzati.  È possibile utilizzare tipi personalizzati nei casi seguenti.  
  
1. Come <xref:System.Windows.PropertyPath> in un data binding. Ad esempio, la <xref:System.Windows.Data.Binding.Path%2A> proprietà di un oggetto <xref:System.Windows.Data.Binding> può fare riferimento a una proprietà di un tipo personalizzato.  
  
2. Come valore della <xref:System.Windows.DataTemplate.DataType%2A> Proprietà.  
  
3. Come tipo che determina le colonne generate automaticamente in un oggetto <xref:System.Windows.Controls.DataGrid> .  
  
<a name="binding_state"></a>
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recupero delle informazioni di data binding da un'espressione di associazione  
 In alcuni casi, è possibile ottenere l'oggetto <xref:System.Windows.Data.BindingExpression> di un oggetto <xref:System.Windows.Data.Binding> e richiedere informazioni sugli oggetti di origine e di destinazione dell'associazione.  Sono state aggiunte nuove API che consentono di ottenere l'oggetto di origine e di destinazione o la proprietà associata.  Quando si dispone di un <xref:System.Windows.Data.BindingExpression> , usare le API seguenti per ottenere informazioni sulla destinazione e sull'origine.  
  
|Per trovare questo valore dell'associazione|Utilizzare questa API|  
|---------------------------------------|------------------|  
|L'oggetto di destinazione|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|La proprietà di destinazione|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Oggetto di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|La proprietà di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Indica se <xref:System.Windows.Data.BindingExpression> appartiene a un oggetto <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Proprietario di un oggetto <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>
## <a name="checking-for-a-valid-datacontext-object"></a>Verifica di un oggetto DataContext valido  
 Ci sono casi in cui l'oggetto <xref:System.Windows.FrameworkElement.DataContext%2A> di un contenitore di elementi in un oggetto <xref:System.Windows.Controls.ItemsControl> viene disconnesso.  Un contenitore di elementi è l'elemento dell'interfaccia utente che visualizza un elemento in un oggetto <xref:System.Windows.Controls.ItemsControl> .  Quando un oggetto <xref:System.Windows.Controls.ItemsControl> è associato a una raccolta, viene generato un contenitore di elementi per ogni elemento. In alcuni casi, i contenitori di elementi vengono rimossi dalla struttura ad albero visuale. Due casi tipici in cui viene rimosso un contenitore di elementi sono quando un elemento viene rimosso dalla raccolta sottostante e quando la virtualizzazione è abilitata in <xref:System.Windows.Controls.ItemsControl> . In questi casi, la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà del contenitore di elementi verrà impostata sull'oggetto sentinel restituito dalla <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> proprietà statica.  È necessario controllare se <xref:System.Windows.FrameworkElement.DataContext%2A> è uguale all' <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> oggetto prima di accedere al <xref:System.Windows.FrameworkElement.DataContext%2A> di un contenitore di elementi.  
  
<a name="live_shaping"></a>
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)  
 Una raccolta di dati può essere raggruppata, ordinata o filtrata. WPF 4.5 consente di riordinare i dati quando questi vengono modificati. Si supponga, ad esempio, che un'applicazione usi un oggetto <xref:System.Windows.Controls.DataGrid> per elencare le scorte in un mercato azionario e che le scorte siano ordinate in base al valore azionario. Se l'ordinamento in tempo reale è abilitato per le scorte <xref:System.Windows.Data.CollectionView> , la posizione di una borsa viene <xref:System.Windows.Controls.DataGrid> spostata quando il valore dell'azione diventa maggiore o minore del valore di un'altra azione.   Per ulteriori informazioni, vedere l' <xref:System.ComponentModel.ICollectionViewLiveShaping> interfaccia.  
  
<a name="weak_event_pattern"></a>
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Supporto migliorato per stabilire un riferimento debole a un evento  
 L'implementazione del modello con riferimenti deboli agli eventi è ora più semplice perché i sottoscrittori di eventi possono parteciparvi senza implementare un'interfaccia aggiuntiva.  La classe generica <xref:System.Windows.WeakEventManager> consente inoltre ai sottoscrittori di partecipare al modello di evento debole se <xref:System.Windows.WeakEventManager> per un determinato evento non esiste una classe dedicata.  Per ulteriori informazioni, vedere [Modelli di eventi deboli](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>
## <a name="new-methods-for-the-dispatcher-class"></a>Nuovi metodi per la classe Dispatcher  
 La classe Dispatcher definisce nuovi metodi per le operazioni sincrone e asincrone.  Il metodo sincrono <xref:System.Windows.Threading.Dispatcher.Invoke%2A> definisce gli overload che accettano un <xref:System.Action> <xref:System.Func%601> parametro o. Il nuovo metodo asincrono, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> , accetta anche un oggetto <xref:System.Action> o <xref:System.Func%601> come parametro di callback e restituisce un oggetto <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601> .   Le <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601> classi e definiscono una <xref:System.Threading.Tasks.Task> Proprietà.  Quando si chiama <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> , è possibile usare la `await` parola chiave con l'oggetto o l'oggetto <xref:System.Windows.Threading.DispatcherOperation> associato <xref:System.Threading.Tasks.Task> . Se è necessario attendere in modo sincrono l'oggetto <xref:System.Threading.Tasks.Task> restituito da <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601> , chiamare il metodo di <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> estensione. La chiamata a comporterà <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> un deadlock se l'operazione viene accodata in un thread chiamante. Per ulteriori informazioni sull'utilizzo di un oggetto <xref:System.Threading.Tasks.Task> per eseguire operazioni asincrone, vedere [Task parallelism (Task Parallel Library)](/dotnet/standard/parallel-programming/task-based-asynchronous-programming).  
  
<a name="events_markup_extenions"></a>
## <a name="markup-extensions-for-events"></a>Estensioni di markup per gli eventi  
 WPF 4.5 supporta le estensioni di markup per gli eventi.  Mentre WPF non definisce un'estensione di markup da utilizzare per gli eventi, le terze parti sono in grado di creare un'estensione di markup che può essere utilizzata con gli eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Novità di .NET Framework](/dotnet/framework/whats-new/index)
