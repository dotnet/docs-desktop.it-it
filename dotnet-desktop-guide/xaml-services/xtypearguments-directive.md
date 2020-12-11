---
title: Direttiva x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969229"
---
# <a name="xtypearguments-directive"></a>Direttiva x:TypeArguments

Passa gli argomenti di tipo vincolante di un oggetto generico al costruttore del tipo generico.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`object`|Dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico CLR. Se `object` fa riferimento a un tipo XAML che non si trova nello spazio dei nomi XAML predefinito, `object` richiede un prefisso per indicare lo spazio dei nomi XAML in cui è `object` presente.|
|`typeString`|Stringa che dichiara uno o più nomi di tipi XAML come stringhe, che fornisce gli argomenti di tipo per il tipo generico CLR. Per ulteriori note sulla sintassi, vedere la sezione Osservazioni.|

## <a name="remarks"></a>Osservazioni

Nella maggior parte dei casi, i tipi XAML usati come elemento informazioni in una `typeString` stringa sono preceduti dal prefisso. I tipi tipici di vincoli CLR generici (ad esempio <xref:System.Int32> e <xref:System.String> ) provengono dalle librerie di classi di base CLR. Tali librerie non sono mappate a spazi dei nomi XAML predefiniti specifici del Framework e pertanto richiedono un mapping di prefisso per l'utilizzo di XAML.

È possibile specificare più di un nome di tipo XAML usando un delimitatore di virgola.

Se i vincoli generici usano tipi generici, gli argomenti del tipo di vincolo annidato possono essere racchiusi tra parentesi ().

Si noti che questa definizione di `x:TypeArguments` è specifica dei servizi XAML .NET e dell'utilizzo del supporto CLR. Una definizione a livello di linguaggio si trova nella [ \[ sezione MS-XAML \] 5.3.11](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Esempi di uso

Per questi esempi, si supponga che siano dichiarate le seguenti definizioni dello spazio dei nomi XAML:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Elenco\<String>

`<scg:List x:TypeArguments="sys:String" ...>` Crea un'istanza di un nuovo oggetto <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.

### <a name="dictionarystringstring"></a>Dizionario\<String,String>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` Crea un'istanza di un nuovo oggetto <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> argomenti di tipo.

### <a name="queuekeyvaluepairstringstring"></a><della coda KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` Crea un'istanza di un nuovo oggetto <xref:System.Collections.Generic.Queue%601> con un vincolo <xref:System.Collections.Generic.KeyValuePair%602> con gli argomenti di tipo di vincolo interno <xref:System.String> e <xref:System.String> .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 e utilizzi XAML generici WPF

Per l'utilizzo di XAML 2006 e XAML usato per le applicazioni WPF, esistono le restrizioni seguenti per gli `x:TypeArguments` utilizzi di tipi generici e di XAML in generale:

- Solo l'elemento radice di un file XAML può supportare un utilizzo generico di XAML che fa riferimento a un tipo generico.

- L'elemento radice deve essere mappato a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>. Le funzioni di pagina rappresentano lo scenario principale per il supporto di utilizzo generico XAML in WPF.

- L'elemento dell'oggetto XAML dell'elemento radice per il generico deve anche dichiarare una classe parziale usando `x:Class` . Questo vale anche se si definisce un'azione di compilazione WPF.

- `x:TypeArguments` non è possibile fare riferimento a vincoli generici annidati.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 o XAML 2006 senza dipendenza WPF 3,0 o WPF 3,5

Nei servizi XAML .NET per XAML 2006 o XAML 2009, le restrizioni correlate a WPF sull'utilizzo generico di XAML sono rilassate. È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il sistema di tipi e il modello a oggetti supportati.

Se si usa XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere i tipi XAML per le primitive di linguaggio comuni, è possibile usare i [tipi incorporati per le primitive del linguaggio XAML comuni](types-for-primitives.md) come elementi informativi in un oggetto `typeString` . Ad esempio, è possibile dichiarare quanto segue (i mapping di prefisso non sono visualizzati, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

In WPF e quando la destinazione è .NET Framework 4 o .NET Core 3,0 (o versione successiva), è possibile usare le funzionalità XAML 2009 insieme a, `x:TypeArguments` ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009. Se è necessario eseguire il markup per compilare il codice XAML, è necessario operare con le restrizioni indicate nella sezione [xaml 2006 e utilizzo di XAML generico WPF](#xaml-2006-and-wpf-generic-xaml-usages) . BAML è supportato solo in .NET Framework.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Estensione del markup x:Type](xtype-markup-extension.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](types-for-primitives.md)
- [Generics in XAML](generics.md)
