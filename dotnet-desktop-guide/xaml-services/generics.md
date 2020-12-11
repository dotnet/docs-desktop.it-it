---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969604"
---
# <a name="generics-in-xaml"></a>Generics in XAML

I servizi XAML di .NET implementati in <xref:System.Xaml?displayProperty=fullName> forniscono supporto per l'utilizzo di tipi CLR generici. Questo supporto include la specifica dei vincoli dei generics come argomento di tipo e l'applicazione del vincolo chiamando il metodo appropriato `Add` per i case di raccolta generici. In questo argomento vengono descritti gli aspetti relativi all'utilizzo e al riferimento a tipi generici in XAML.

## <a name="xtypearguments"></a>x:TypeArguments

`x:TypeArguments` è una direttiva definita dal linguaggio XAML. Quando viene usato come membro di un tipo XAML supportato da un tipo generico, `x:TypeArguments` passa gli argomenti di tipo vincolante dell'oggetto generico al costruttore sottostante. Per la sintassi di riferimento relativa all'utilizzo dei servizi XAML .NET di `x:TypeArguments` , che include esempi di sintassi, vedere [x:TypeArguments Directive](xtypearguments-directive.md).

Poiché `x:TypeArguments` accetta una stringa e ha il supporto del convertitore di tipi, viene in genere dichiarata nell'utilizzo XAML come attributo.

Nel flusso di nodi XAML, le informazioni dichiarate da `x:TypeArguments` possono essere ottenute da in <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> una `StartObject` posizione nel flusso del nodo. Il valore restituito di <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> è un elenco di <xref:System.Xaml.XamlType> valori. La decisione di determinare se un tipo XAML rappresenti un tipo generico può essere eseguita chiamando <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType> .

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regole e convenzioni di sintassi per i generics in XAML

In XAML un tipo generico deve essere sempre rappresentato come generico vincolato. Un generico non vincolato non è mai presente nel sistema di tipi XAML o in un flusso di nodi XAML e non può essere rappresentato nel markup XAML. È possibile fare riferimento a un generico nella sintassi dell'attributo XAML per i casi in cui si tratta di un vincolo di tipo annidato di un oggetto generico a cui viene fatto riferimento da `x:TypeArguments` o nei casi in cui `x:Type` fornisce un riferimento a un tipo CLR per un tipo generico. Il riferimento ai generics è supportato tramite la <xref:System.Xaml.Schema.XamlTypeTypeConverter> classe definita dai servizi XAML di .NET.

Il formato di sintassi dell'attributo XAML abilitato da <xref:System.Xaml.Schema.XamlTypeTypeConverter> modifica la convenzione di sintassi MSIL/CLR tipica che utilizza le parentesi angolari per i tipi e i vincoli dei generics e sostituisce invece le parentesi per il contenitore di vincoli. Per un esempio, vedere [X:TypeArguments Directive](xtypearguments-directive.md).

## <a name="generics-and-xaml-2009-features"></a>Generics e funzionalità XAML 2009

Se si usa XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere i tipi XAML per le primitive di linguaggio comuni, è possibile usare i [tipi incorporati xaml 2009](types-for-primitives.md) come elementi di informazioni in `x:TypeArguments` . Ad esempio, è possibile dichiarare quanto segue (i mapping di prefisso non sono visualizzati, ma `x` è lo spazio dei nomi XAML del linguaggio XAML per xaml 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>Supporto di generics in WPF

Per l'utilizzo di XAML 2006 quando si specifica specificamente come destinazione WPF, è necessario fornire anche [x:Class](xclass-directive.md) sullo stesso elemento di `x:TypeArguments` e tale elemento deve essere l'elemento radice in un documento XAML. L'elemento radice deve essere mappato a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.

Le soluzioni alternative possibili per supportare gli utilizzi generici includono la definizione di un'estensione di markup personalizzata che può restituire tipi generici o la definizione di una classe di wrapping che deriva da un tipo generico, ma rende flat il vincolo generico nella relativa definizione di classe.

In WPF è possibile usare le funzionalità XAML 2009 insieme a `x:TypeArguments` , ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.

I flussi di lavoro personalizzati in Windows Workflow Foundation per .NET Framework 3,5 non supportano l'utilizzo generico di XAML.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:TypeArguments](xtypearguments-directive.md)
- [Direttiva x:Class](xclass-directive.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](types-for-primitives.md)
