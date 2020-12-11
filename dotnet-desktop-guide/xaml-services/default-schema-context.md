---
title: Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969619"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>Contesto dello schema XAML predefinito e contesto dello schema XAML WPF
Un contesto dello schema XAML è un'entità concettuale che qualifica il modo in cui una produzione XAML che usa un particolare vocabolario XAML interagisce con il comportamento di scrittura dell'oggetto, incluso il modo in cui vengono risolti i mapping dei tipi, il modo in cui vengono caricati gli assembly, le impostazioni di lettura e scrittura. In questo argomento vengono descritte le funzionalità dei servizi XAML .NET e il contesto dello schema XAML predefinito associato, basato sul sistema di tipi CLR. In questo argomento viene inoltre descritto il contesto dello schema XAML utilizzato per WPF.

## <a name="default-xaml-schema-context"></a>Contesto dello schema XAML predefinito

I servizi XAML .NET implementano e usano un contesto dello schema XAML predefinito. Il comportamento del contesto dello schema XAML predefinito non è sempre completamente visibile nell'API della <xref:System.Xaml.XamlSchemaContext> classe. In molti casi, tuttavia, il comportamento influenzato dal contesto dello schema XAML predefinito è osservabile tramite l'API comune del sistema di tipi XAML, ad esempio i membri di <xref:System.Xaml.XamlMember> o <xref:System.Xaml.XamlType> , o tramite API esposte su reader XAML e writer XAML che usano il contesto dello schema XAML predefinito.

È possibile creare un oggetto <xref:System.Xaml.XamlSchemaContext> che incapsula il comportamento predefinito chiamando il <xref:System.Xaml.XamlSchemaContext> costruttore. Viene creato in modo esplicito il contesto dello schema XAML predefinito. Lo stesso contesto dello schema XAML predefinito viene creato in modo implicito, se si Inizializza un reader XAML o un writer XAML usando le API che non accettano esplicitamente un <xref:System.Xaml.XamlSchemaContext> parametro di input.

Il contesto dello schema XAML predefinito si basa sulla reflection CLR per il relativo comportamento di mapping dei tipi. Questa operazione include l'analisi del CLR <xref:System.Type> di definizione e dei relativi <xref:System.Reflection.PropertyInfo> o <xref:System.Reflection.MethodInfo> . Inoltre, l'attribuzione di CLR per i tipi o i membri viene utilizzata per inserire le specifiche per il tipo XAML o informazioni sui membri XAML che utilizzano il tipo di supporto CLR. Il contesto dello schema XAML predefinito non richiede tecniche di estensione del sistema di tipi, ad esempio il `Invoker` modello, perché le informazioni necessarie sono disponibili dal sistema di tipi CLR.

Per la logica di caricamento degli assembly, il contesto dello schema XAML predefinito si basa principalmente su qualsiasi valore di assembly fornito nei mapping dello spazio dei nomi XAML. Inoltre, <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> può suggerire un assembly da caricare, per scenari come il caricamento di tipi interni.

## <a name="wpf-xaml-schema-context"></a>Contesto dello schema XAML WPF

Il contesto dello schema XAML WPF viene descritto in questo argomento perché l'implementazione di WPF fornisce un'illustrazione interessante dei tipi di funzionalità che possono essere introdotti implementando un contesto dello schema XAML non predefinito. Il concetto di contesto dello schema XAML, inoltre, non viene discusso molto nella documentazione di WPF che indirizza il codice XAML WPF; il comportamento abilitato dal contesto dello schema XAML può essere completamente comprensibile solo se integrato con una discussione sul funzionamento del contesto dello schema XAML predefinito. Il contesto dello schema XAML WPF implementa il comportamento seguente.

**Override ricerca:** WPF include alcuni modelli di contenuto per XAML in cui sono presenti proprietà di contenuto XAML che funzionano senza essere <xref:System.Windows.Markup.ContentPropertyAttribute> attribuite. <xref:System.Xaml.XamlType.LookupContentProperty%2A> le sostituzioni per WPF implementano questo comportamento.

**Rinvio per le espressioni WPF:** WPF include diverse classi di espressioni che rinviano un valore fino a quando non è disponibile un contesto di Runtime. Inoltre, l'espansione del modello è un comportamento di runtime che si basa sulle tecniche di rinvio.

**Ottimizzazioni di ricerca del sistema di tipi:** WPF include un ampio vocabolario XAML e un modello a oggetti, incluse le definizioni dei membri della classe di base che ereditano letteralmente centinaia di classi definite da WPF. Inoltre, WPF è distribuito in diversi assembly. WPF ottimizza la ricerca dei tipi usando le tabelle di ricerca e altre tecniche. Ciò consente di migliorare le prestazioni rispetto al contesto dello schema XAML predefinito e alla relativa ricerca dei tipi basata su CLR. Nei casi in cui i tipi non esistono in una tabella di ricerca, il comportamento utilizza tecniche del contesto dello schema XAML simili al contesto dello schema XAML predefinito.

**XamlType e XamlMember Extension:** WPF estende i concetti di proprietà con le proprietà di dipendenza e i concetti di evento con gli eventi indirizzati. Per fornire a questi concetti una maggiore visibilità per le operazioni di elaborazione XAML, WPF estende <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember> aggiunge proprietà interne che segnalano la proprietà di dipendenza e le caratteristiche degli eventi indirizzati.

### <a name="accessing-the-wpf-xaml-schema-context"></a>Accesso al contesto dello schema XAML WPF

Se si utilizzano tecniche XAML basate su WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> o <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType> , il contesto dello schema XAML WPF è già in uso in tali implementazioni del reader XAML e del writer XAML.

Se si usano altre implementazioni del reader XAML o del writer XAML che non vengono inizializzate con il contesto dello schema XAML WPF, potrebbe essere possibile ottenere un contesto dello schema XAML WPF funzionante da <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType> . È quindi possibile usare questo valore come inizializzazione per altre API che usano un <xref:System.Xaml.XamlSchemaContext> . Ad esempio, è possibile chiamare <xref:System.Xaml.XamlXmlReader.%23ctor%2A> per l'inizializzazione e passare il contesto dello schema XAML WPF. In alternativa, è possibile usare il contesto dello schema XAML WPF per le operazioni del sistema di tipi XAML. Ciò può includere l'inizializzazione della costruzione di un oggetto <xref:System.Xaml.XamlType> o <xref:System.Xaml.XamlMember> o la chiamata di <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType> .

Si noti che se si accede a determinati aspetti del codice XAML WPF da prospettive flusso di nodi XAML pure, alcune delle funzionalità del framework WPF potrebbero non essere ancora state eseguite. Ad esempio, i modelli WPF per i controlli non sono ancora stati applicati. Pertanto, se si accede a una proprietà che in fase di esecuzione potrebbe essere popolata con una struttura ad albero visuale completa, è possibile che venga visualizzato solo un valore della proprietà che fa riferimento a un modello. Il contesto del servizio fornito per le estensioni di markup WPF potrebbe anche non essere accurato se fornito da una situazione di non runtime e può causare eccezioni durante il tentativo di scrittura di un oggetto grafico.

## <a name="xaml-and-assembly-loading"></a>Caricamento di assembly e XAML

Il caricamento degli assembly per i servizi XAML e .NET XAML si integra con il concetto definito da CLR di <xref:System.AppDomain> . Un contesto dello schema XAML interpreta come caricare assembly o trovare tipi in fase di esecuzione o di progettazione, in base all'utilizzo di <xref:System.AppDomain> e ad altri fattori. La logica è leggermente diversa a seconda che XAML sia un XAML separato per un reader XAML, che sia XAML compilato in una DLL da `XamlBuildTask` o sia BAML generato da WPF `PresentationBuildTask` .

Il contesto dello schema XAML per WPF si integra con il modello di applicazione WPF, che a sua volta USA, oltre ad <xref:System.AppDomain> altri fattori che sono dettagli di implementazione WPF.

#### <a name="xaml-reader-input-loose-xaml"></a>Input reader XAML (codice XAML separato)

01. Il contesto dello schema XAML scorre l'oggetto <xref:System.AppDomain> dell'applicazione, cercando un assembly già caricato che corrisponda a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, l'assembly viene usato per la risoluzione.

02. In caso contrario, viene usata una delle tecniche seguenti basate sull' <xref:System.Reflection.Assembly> API CLR per caricare un assembly:

    - Se il nome è qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> per il nome completo.

    - Se il passaggio precedente ha esito negativo, usare il nome breve (e il token di chiave pubblica se presente) per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> .

    - Se il nome non è qualificato nel mapping, chiamare <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> .

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask` viene utilizzato per Windows Communication Foundation (WCF) e Windows Workflow Foundation.

Si noti che i riferimenti agli assembly tramite `XamlBuildTask` sono sempre completi.

1. Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> il nome completo.

2. Se il passaggio precedente ha esito negativo, usare il nome breve (e il token di chiave pubblica se presente) per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> .

#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)

Per il caricamento di assembly per BAML sono presenti due aspetti: il caricamento dell'assembly iniziale che contiene il BAML come componente e il caricamento degli assembly di backup del tipo per tutti i tipi a cui fa riferimento la produzione BAML.

##### <a name="assembly-load-for-initial-markup"></a>Caricamento assembly per markup iniziale:

Il riferimento all'assembly da cui caricare il markup è sempre non qualificato.

1. Il contesto dello schema XAML WPF scorre l'oggetto <xref:System.AppDomain> dell'applicazione WPF, cercando un assembly già caricato che corrisponda a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, l'assembly viene usato per la risoluzione.

2. Se il passaggio precedente ha esito negativo, usare il nome breve (e il token di chiave pubblica se presente) per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> .

##### <a name="assembly-references-by-baml-types"></a>Riferimenti ad assembly per tipi BAML:

I riferimenti ad assembly per i tipi utilizzati nell'ambiente di produzione BAML sono sempre completi, come output dell'attività di compilazione.

01. Il contesto dello schema XAML WPF scorre l'oggetto <xref:System.AppDomain> dell'applicazione WPF, cercando un assembly già caricato che corrisponda a tutti gli aspetti del nome, a partire dall'assembly caricato più di recente. Se viene trovata una corrispondenza, l'assembly viene usato per la risoluzione.

02. In caso contrario, per caricare un assembly viene utilizzata una delle tecniche seguenti:

    - Chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> il nome completo.
  
    - Se una combinazione di nome breve e token di chiave pubblica corrisponde all'assembly da cui è stato caricato il BAML, utilizzare tale assembly.

    - Usare nome breve e token di chiave pubblica per chiamare <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> .

## <a name="see-also"></a>Vedere anche

- [Informazioni su strutture e concetti del flusso del nodo XAML](understanding-xaml-node-stream-structures-and-concepts.md)
