---
title: Direttiva x:Class
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: feada5fa118f3f39170a4d269155e71a56f5b085
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969049"
---
# <a name="xclass-directive"></a>Direttiva x:Class

Configura la compilazione del markup XAML per unire classi parziali tra markup e code-behind. La classe parziale del codice è definita in un file di codice separato in un linguaggio Common Language Specification (CLS), mentre la classe parziale di markup viene in genere creata dalla generazione del codice durante la compilazione XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`namespace`|facoltativo. Specifica uno spazio dei nomi CLR che contiene la classe parziale identificata da `classname` . Se `namespace` si specifica, un punto (.) separa `namespace` e `classname` . Vedere la sezione Osservazioni.|
|`classname`|Obbligatorio. Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per il codice XAML.|

## <a name="dependencies"></a>Dependencies

`x:Class` può essere specificato solo sull'elemento radice di una produzione XAML. `x:Class` non è valido per qualsiasi oggetto con un elemento padre nella produzione XAML. Per ulteriori informazioni, vedere la [ \[ sezione MS-XAML \] 4.3.1.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="remarks"></a>Osservazioni

Il `namespace` valore può contenere punti aggiuntivi per organizzare gli spazi dei nomi correlati in gerarchie di nomi, una tecnica comune nella programmazione .NET. Solo l'ultimo punto in una stringa di `x:Class` valori viene interpretato come separato `namespace` e `classname.` la classe usata come `x:Class` non può essere una classe annidata. Le classi annidate non sono consentite perché la determinazione del significato dei punti per le `x:Class` stringhe è ambigua se sono consentite classi annidate.

Nei modelli di programmazione esistenti che usano `x:Class` , `x:Class` è facoltativo nel senso che è interamente valido avere una pagina XAML senza code-behind. Questa funzionalità, tuttavia, interagisce con le azioni di compilazione implementate dai Framework che usano XAML. `x:Class` la funzionalità è influenzata anche dai ruoli che varie classificazioni del contenuto specificato in XAML hanno in un modello di applicazione e nelle azioni di compilazione corrispondenti. Se il codice XAML dichiara i valori degli attributi di gestione degli eventi o crea un'istanza di elementi personalizzati in cui le classi di definizione si trovano nella classe code-behind, è necessario fornire il `x:Class` riferimento alla direttiva (o [x:Subclass](xsubclass-directive.md)) alla classe appropriata per il code-behind.

Il valore della `x:Class` direttiva deve essere una stringa che specifica il nome completo di una classe ma senza informazioni sull'assembly (equivalente a <xref:System.Type.FullName%2A?displayProperty=nameWithType> ). Per le applicazioni semplici, è possibile omettere le informazioni sullo spazio dei nomi CLR se il code-behind è anche strutturato in questo modo (la definizione del codice inizia a livello di classe).

Il file code-behind per una definizione di pagina o di applicazione deve trovarsi all'interno di un file di codice incluso come parte del progetto che produce un'applicazione compilata e implica la compilazione del markup. È necessario seguire le regole dei nomi per le classi CLR. Per ulteriori informazioni, vedere [linee guida](/dotnet/api/)per la progettazione di Framework. Per impostazione predefinita, la classe code-behind deve essere. `public` tuttavia, è possibile definirla a un livello di accesso diverso usando la [direttiva x:ClassModifier](xclassmodifier-directive.md).

Questa interpretazione dell' `x:Class` attributo si applica solo a un'implementazione XAML basata su CLR, in particolare ai servizi XAML .NET. Altre implementazioni XAML che non sono basate su CLR e che non utilizzano servizi XAML .NET potrebbero utilizzare una formula di risoluzione diversa per la connessione del markup XAML e il codice di run-time di backup. Per ulteriori informazioni sulle interpretazioni più generali di `x:Class` , vedere [ \[ MS-XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

A un certo livello di architettura, il significato di non `x:Class` è definito nei servizi XAML .NET. Questo perché i servizi XAML di .NET non specificano il modello di programmazione in base al quale sono connessi il markup XAML e il codice di supporto. Altri usi della `x:Class` direttiva potrebbero essere implementati da framework specifici che usano modelli di programmazione o modelli di applicazione per definire come connettere il markup XAML e il code-behind basato su CLR. Ogni Framework può avere proprie azioni di compilazione che abilitano parte del comportamento o componenti specifici che devono essere inclusi nell'ambiente di compilazione. All'interno di un Framework, le azioni di compilazione possono variare anche in base al linguaggio CLR specifico usato per il code-behind.

## <a name="xclass-in-the-wpf-programming-model"></a>x:Class nel modello di programmazione WPF

Nelle applicazioni WPF e nel modello di applicazione WPF, `x:Class` può essere dichiarato come attributo per qualsiasi elemento che è la radice di un file XAML e viene compilato (dove il codice XAML è incluso in un progetto di applicazione WPF con `Page` azione di compilazione) o per la <xref:System.Windows.Application> radice nella definizione dell'applicazione di un'applicazione WPF compilata. La Dichiarazione `x:Class` di un elemento diverso da una radice di pagina o di un'applicazione o da un file XAML WPF non compilato causa un errore in fase di compilazione sotto il compilatore XAML wpf .NET Framework 3,0 e .NET Framework 3,5. Per informazioni su altri aspetti della `x:Class` gestione in WPF, vedere [code-behind e XAML in WPF](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="xclass-for-windows-workflow-foundation"></a>x:Class per Windows Workflow Foundation

Per Windows Workflow Foundation, `x:Class` assegna un nome alla classe di un'attività personalizzata composta interamente in XAML o assegna un nome alla classe parziale della pagina XAML per un ActivityDesigner con code-behind.

## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight

`x:Class` per Silverlight è documentato separatamente. Per altre informazioni, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Subclass](xsubclass-directive.md)
- [Classi XAML e personalizzate per WPF](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Direttiva x:ClassModifier](xclassmodifier-directive.md)
- [Tipi migrati da WPF a System.Xaml](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
