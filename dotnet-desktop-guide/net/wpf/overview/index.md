---
title: Informazioni Windows Presentation Foundation
description: In questo articolo viene fornita una panoramica su quale Windows Presentation Foundation (WPF) è correlato a .NET e quali funzionalità sono disponibili.
ms.date: 07/18/2019
ms.topic: overview
ms.openlocfilehash: f548299dd259ab5f52962660cc7e342396e20213
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969655"
---
# <a name="what-is-windows-presentation-foundation-wpf-net"></a>Informazioni su Windows Presentation Foundation (WPF .NET)

Benvenuti nella Guida al desktop per Windows Presentation Foundation (WPF), un Framework dell'interfaccia utente che crea applicazioni client desktop per Windows. La piattaforma di sviluppo WPF supporta un'ampia gamma di funzionalità di sviluppo di applicazioni, tra cui un modello di applicazione, controlli, grafica e data binding. WPF USA Extensible Application Markup Language (XAML) per fornire un modello dichiarativo per la programmazione di applicazioni.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Esistono due implementazioni di WPF:

01. Implementazione open source ospitata in [GitHub](https://github.com/dotnet/wpf). Questa versione viene eseguita in .NET Core 3,0. La finestra di progettazione visiva WPF per XAML richiede almeno [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide).

01. Implementazione di .NET Framework supportata da Visual Studio 2019 e Visual Studio 2017.

Questa guida al desktop è scritta per .NET Core 3,0 e WPF. Per ulteriori informazioni sulla documentazione esistente per WPF con la .NET Framework, vedere [Windows Presentation Foundation di Framework](../../../framework/wpf/index.md).

## <a name="xaml"></a>XAML

XAML è un linguaggio dichiarativo basato su XML utilizzato da WPF per elementi come la definizione di risorse o di elementi dell'interfaccia utente. Gli elementi definiti in XAML rappresentano la creazione di istanze di oggetti da un assembly. XAML è diverso dalla maggior parte degli altri linguaggi di markup, che vengono interpretati in fase di esecuzione senza un vincolo diretto a un sistema di tipi di supporto.

Nell'esempio seguente viene illustrato come creare un pulsante come parte di un'interfaccia utente. Questo esempio ha lo scopo di fornire un'idea del modo in cui XAML rappresenta un oggetto, dove `Button` è il tipo ed `Content` è una proprietà.

```xaml
<StackPanel>
    <Button Content="Click Me!" />
</StackPanel>
```

<!--For more information, see [XAML overview (WPF)](../../../framework/wpf/advanced/xaml-overview-wpf.md).-->

### <a name="xaml-extensions"></a>Estensioni XAML

XAML fornisce la sintassi per le estensioni di markup. È possibile usare le estensioni di markup per fornire valori per le proprietà in forma di attributo, form elemento proprietà o entrambi.

Il codice XAML precedente, ad esempio, ha definito un pulsante con il contenuto visibile impostato sulla stringa letterale `"Click Me!"` , ma il contenuto può invece essere impostato da un'estensione di markup supportata. Un'estensione di markup viene definita con parentesi graffe di apertura e chiusura `{ }` . Il tipo di estensione di markup viene quindi identificato dal token di stringa immediatamente successivo alla parentesi graffa di apertura.

```xaml
<StackPanel>
    <Button Content="{MarkupType}" />
</StackPanel>
```

WPF fornisce diverse estensioni di markup per XAML, ad esempio `{Binding}` per data binding.

Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="property-system"></a>Sistema di proprietà

In WPF è disponibile un set di servizi che possono essere utilizzati per estendere la funzionalità della [Proprietà](/dotnet/standard/base-types/common-type-system#properties)di un tipo. Complessivamente, questi servizi vengono definiti come il sistema di *proprietà WPF*. Una proprietà supportata dal sistema di proprietà WPF è nota come proprietà di dipendenza.

Le proprietà di dipendenza estendono le funzionalità della proprietà fornendo il <xref:System.Windows.DependencyProperty> tipo che esegue il backup di una proprietà. Il tipo di proprietà di dipendenza è un'implementazione alternativa del modello standard di backup della proprietà con un campo privato.

### <a name="dependency-property"></a>Proprietà di dipendenza

In WPF, le proprietà di dipendenza vengono in genere esposte come [Proprietà](/dotnet/standard/base-types/common-type-system#properties).NET standard. A un livello di base, è possibile interagire direttamente con queste proprietà senza mai saperlo che sono implementate come proprietà di dipendenza.

Lo scopo delle proprietà di dipendenza consiste nel fornire un modo per calcolare il valore di una proprietà in base al valore di altri input. Questi altri input possono includere proprietà di sistema, ad esempio temi e preferenze dell'utente, o proprietà just-in-time da data binding e animazioni.

Una proprietà di dipendenza può essere implementata per fornire la convalida, i valori predefiniti e i callback che monitorano le modifiche ad altre proprietà. Le classi derivate possono anche modificare alcune caratteristiche specifiche di una proprietà esistente eseguendo l'override dei metadati della proprietà di dipendenza, anziché creare una nuova proprietà o eseguire l'override di una proprietà esistente.

### <a name="dependency-object"></a>Oggetto Dependency

Un altro tipo che è chiave per il sistema di proprietà WPF è <xref:System.Windows.DependencyObject> . Questo tipo definisce la classe di base che può registrare e possedere una proprietà di dipendenza. I <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> metodi e forniscono l'implementazione di supporto della proprietà di dipendenza per l'istanza dell'oggetto di dipendenza.

Nell'esempio seguente viene illustrato un oggetto dipendenza che definisce un singolo identificatore di proprietà di dipendenza denominato `ValueProperty` . La proprietà di dipendenza viene creata con la `Value` Proprietà .NET.

```csharp
public class TextField: DependencyObject
{
    public static readonly DependencyProperty ValueProperty =
        DependencyProperty.Register("Value", typeof(string), typeof(TextField), new PropertyMetadata(""));

    public string Value
    {
        get { return (string)GetValue(ValueProperty); }
        set { SetValue(ValueProperty, value); }
    }
}
```

La proprietà di dipendenza è definita come membro statico di un tipo di oggetto di dipendenza, ad `TextField` esempio nell'esempio precedente. La proprietà di dipendenza deve essere registrata con l'oggetto dipendenza.

La `Value` proprietà nell'esempio precedente esegue il wrapping della proprietà di dipendenza, specificando il modello di proprietà .NET standard a cui si è probabilmente abituati.

<!--For more information, see [Dependency properties overview](../../../framework/wpf/advanced/dependency-properties-overview.md).-->

## <a name="events"></a>Eventi

WPF fornisce un sistema di gestione degli eventi sovrapposto agli eventi .NET Common Language Runtime (CLR) con cui si ha familiarità. Questi eventi WPF sono detti eventi indirizzati.

Un evento indirizzato è un evento CLR supportato da un'istanza della `RoutedEvent` classe e registrato con il sistema di eventi WPF. L' `RoutedEvent` istanza ottenuta dalla registrazione degli eventi viene in genere mantenuta come `public static readonly` membro del campo della classe che esegue la registrazione e quindi *possiede* l'evento indirizzato. La connessione all'evento CLR con nome identico (a volte definito evento *wrapper* ) viene eseguita eseguendo l'override delle `add` `remove` implementazioni e per l'evento CLR. Il meccanismo di backup e di connessione degli eventi indirizzati è concettualmente simile al modo in cui una [proprietà di dipendenza](#dependency-property) è una proprietà CLR supportata dalla `DependencyProperty` classe e registrata con il sistema di proprietà WPF.

Il vantaggio principale del sistema di eventi indirizzati consiste nel fatto che gli eventi vengono *propagati* nell'albero degli elementi del controllo che cerca un gestore. Poiché, ad esempio, WPF include un modello di contenuto avanzato, è possibile impostare un controllo immagine come contenuto di un controllo Button. Quando si fa clic con il mouse sul controllo immagine, si prevede che utilizzi gli eventi del mouse e quindi interrompano gli hit test che causano la chiamata dell'evento da parte di un pulsante `Click` . In un modello di eventi CLR tradizionale, è possibile aggirare questa limitazione connettendo lo stesso gestore sia all'immagine che al pulsante. Tuttavia, con il sistema di eventi indirizzati, gli eventi del mouse richiamati sul controllo immagine, ad esempio la selezione, si propagano fino al controllo pulsante padre.

<!--For more information, including other types of event models, see [Events overview](../../../framework/wpf/advanced/routed-events-overview.md).-->

## <a name="data-binding"></a>Associazione dati

WPF data binding offre un modo semplice e coerente per le applicazioni di presentare e interagire con i dati. Gli elementi possono essere associati a dati di diversi tipi di origini dati sotto forma di oggetti Common Language Runtime (CLR) e XML. WPF fornisce anche un meccanismo per il trasferimento dei dati tramite operazioni di trascinamento della selezione.

L'associazione dati è il processo che stabilisce una connessione tra l'interfaccia utente dell'applicazione e la logica di business. Se l'associazione presenta le impostazioni corrette e i dati forniscono le notifiche appropriate, quando i dati cambiano il relativo valore, gli elementi associati ai dati riflettono automaticamente le modifiche. Il Data Binding può anche significare che se una rappresentazione esterna dei dati in un elemento viene modificata, i dati sottostanti vengono aggiornati automaticamente per riflettere la modifica. Se, ad esempio, l'utente modifica il valore in un elemento TextBox, il valore dei dati sottostanti verrà aggiornato automaticamente per riflettere la modifica.

Il Data Binding può essere configurato in XAML tramite l' `{Binding}` estensione di markup. Nell'esempio seguente viene illustrata l'associazione alla proprietà di un oggetto dati `ButtonText` . Se l'associazione ha esito negativo, `Click Me!` viene usato il valore di.

```xaml
<StackPanel>
    <Button Content="{Binding ButtonText, FallbackValue='Click Me!'}" />
</StackPanel>
```

Per altre informazioni, vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md).

## <a name="ui-components"></a>componenti dell'interfaccia utente

WPF fornisce molti dei componenti dell'interfaccia utente comuni utilizzati in quasi tutte le applicazioni Windows, ad esempio `Button` , `Label` , `TextBox` , `Menu` e `ListBox` . In passato, questi oggetti sono stati indicati come controlli. Mentre WPF SDK continua a usare il termine controllo per indicare in modo generico qualsiasi classe che rappresenta un oggetto visibile in un'applicazione, è importante notare che una classe non deve ereditare dalla `Control` classe per avere una presenza visibile. Le classi che ereditano dalla `Control` classe contengono `ControlTemplate` , che consente al consumer di un controllo di modificare radicalmente l'aspetto del controllo senza dover creare una nuova sottoclasse.

## <a name="styles-and-templates"></a>Stili e modelli

Gli stili e i modelli WPF fanno riferimento a una suite di funzionalità (stili, modelli, trigger e storyboard) che consentono a un'applicazione, a un documento o a una finestra di progettazione dell'interfaccia utente di creare applicazioni visivamente accattivanti e di standardizzare una particolare ricerca del proprio prodotto.

Un'altra funzionalità del modello di stile WPF è la separazione tra presentazione e logica, il che significa che i progettisti possono lavorare sull'aspetto di un'applicazione con XAML mentre gli sviluppatori lavorano sulla logica di programmazione in un'altra posizione.

Inoltre, è importante comprendere le risorse, che consentono di riutilizzare gli stili e i modelli.

Per altre informazioni, vedere [stili e modelli](../fundamentals/styles-templates-overview.md).

## <a name="resources"></a>Risorse

Le risorse WPF sono oggetti che possono essere riutilizzati in posizioni diverse dell'applicazione. Esempi di risorse includono stili, modelli e pennelli colori. È possibile definire e fare riferimento alle risorse nel codice e nel formato XAML.

Ogni elemento a livello di Framework ( <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> ) ha una `Resources` Proprietà (che è un <xref:System.Windows.ResourceDictionary> tipo) che contiene le risorse definite. Poiché tutti gli elementi ereditano da un elemento a livello di Framework, tutti gli elementi possono definire risorse. Tuttavia, per definire le risorse in un elemento radice di un documento XAML è più comune.

<!--For more information, see [XAML Resources](../../../framework/wpf/advanced/xaml-resources.md).-->

## <a name="next-steps"></a>Passaggi successivi

- [Creare un'applicazione WPF.](/visualstudio/get-started/csharp/tutorial-wpf?bc=%252fdotnet%252fbreadcrumb%252ftoc.json&toc=%252fdotnet%252fdesktop-wpf%252ftoc.json)
- [Esaminare le differenze rispetto a .NET Framework.](../migration/differences-from-net-framework.md)
- [Informazioni su XAML.](../fundamentals/xaml.md)
