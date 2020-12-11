---
title: Raccolte e tipi di raccolte per XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969622"
---
# <a name="collections-and-collection-types-for-xaml"></a>Raccolte e tipi di raccolta per XAML

Questo articolo descrive come definire le proprietà dei tipi destinati a supportare una raccolta e per supportare la sintassi XAML per creare un'istanza di elementi della raccolta come elementi figlio di un elemento oggetto padre o elemento Property.

## <a name="xaml-collection-concepts"></a>Concetti relativi alla raccolta XAML

Dal punto di vista concettuale, qualsiasi relazione in XAML in cui sono presenti più elementi figlio all'interno dell'ambito di un elemento oggetto XAML o di una proprietà XAML deve essere implementata come raccolta. Tale raccolta deve essere associata a una particolare proprietà XAML del tipo XAML che rappresenta l'elemento padre in quella relazione. La proprietà deve essere una raccolta perché un processore XAML prevede di assegnare a ogni elemento del markup un elemento appena aggiunto della proprietà della raccolta sottostante.

A livello di linguaggio XAML, i requisiti esatti del supporto per la raccolta non sono completamente definiti. Il concetto che una raccolta può essere un elenco o un dizionario (ma non entrambi) viene definito a livello di linguaggio XAML, ma i tipi di supporto rappresentano elenchi o dizionari non sono definiti dal linguaggio XAML.

Nei servizi XAML di .NET, il concetto di supporto della raccolta XAML è definito in modo più chiaro in termini di tipi di backup .NET. In particolare, il supporto XAML per le raccolte si basa su diversi concetti e API .NET utilizzati per elenchi e dizionari nella programmazione .NET generale.

1. L' <xref:System.Collections.IList> interfaccia indica una raccolta di elenchi.

2. L' <xref:System.Collections.IDictionary> interfaccia indica una raccolta di dizionari.

3. <xref:System.Array> rappresenta una matrice e una matrice supporta i <xref:System.Collections.IList> metodi.

In ognuno di questi concetti di raccolta, un processore XAML di servizi XAML .NET prevede di chiamare il `Add` metodo su un'istanza specifica del tipo della proprietà della raccolta. In alternativa, in uno scenario di serializzazione, un processore XAML produce istanze discrete di tipo XAML per ogni elemento presente nell'elenco, nel dizionario o nella matrice in base al concetto specifico di "Items" della raccolta. Questi elementi sono: <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType> ; <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType> ; esplicito <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> per <xref:System.Array> .

## <a name="generic-collections"></a>Raccolte generiche

Le raccolte generiche possono essere utili per la programmazione .NET generale e possono essere usate anche per le proprietà della raccolta XAML. Tuttavia, le interfacce generiche <xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602> non vengono identificate dai processori XAML dei servizi XAML di .NET come equivalenti all'oggetto o non generico <xref:System.Collections.IList> <xref:System.Collections.IDictionary> . Anziché implementare le interfacce, un approccio consigliato per i tipi di proprietà della raccolta generica consiste nel derivare dalle classi <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602> . Queste classi implementano le interfacce non generiche e quindi includono il supporto previsto per le raccolte XAML nell'implementazione di base.

## <a name="read-only-collections-and-initialization-logic"></a>Raccolte di Read-Only e logica di inizializzazione

Nella programmazione .NET, si tratta di un modello di progettazione comune per rendere qualsiasi proprietà che contenga un valore di una raccolta come raccolta di sola lettura. Questo modello consente all'istanza proprietaria della proprietà della raccolta di controllare meglio cosa accade alla raccolta. In particolare, il modello impedisce la sostituzione accidentale dell'intera raccolta preesistente impostando la proprietà. In questo modello, qualsiasi accesso alla raccolta da parte dei chiamanti deve essere eseguito chiamando metodi o proprietà come supportato dal tipo di raccolta e/o le interfacce di raccolta pertinenti, ad esempio <xref:System.Collections.IList> .

L'utilizzo di questo modello implica che qualsiasi classe che espone una proprietà di raccolta di sola lettura deve innanzitutto inizializzare tale proprietà in modo che contenga una raccolta vuota. In genere l'inizializzazione viene eseguita come parte del comportamento di costruzione per la classe. Per essere utile per XAML, è importante che tale logica faccia sempre riferimento al costruttore senza parametri, perché XAML chiama in genere il costruttore senza parametri prima di elaborare le proprietà (proprietà della raccolta o in caso contrario).

## <a name="xaml-type-system-support-and-collections"></a>Raccolte e supporto del sistema di tipi XAML

Oltre ai meccanismi di base per l'analisi di XAML e il popolamento o la serializzazione delle proprietà della raccolta, il sistema di tipi XAML implementato nei servizi XAML di .NET include diverse funzionalità di progettazione relative alle raccolte in XAML.

1. <xref:System.Xaml.XamlType.IsCollection%2A> Restituisce true se il tipo XAML è supportato da un tipo che fornisce il supporto per la raccolta XAML.

2. <xref:System.Xaml.XamlType.IsDictionary%2A> e <xref:System.Xaml.XamlType.IsArray%2A> possono identificare ulteriormente la modalità di raccolta supportata dal tipo XAML. Per i processori XAML personalizzati basati sui servizi XAML .NET e sul sistema di tipi XAML, ma non sulla base delle <xref:System.Xaml.XamlWriter> implementazioni esistenti, la conoscenza della modalità di raccolta utilizzata potrebbe essere necessaria per conoscere il metodo da richiamare per l'elaborazione della raccolta.

3. Ognuno dei valori di proprietà precedenti è potenzialmente influenzato dalle sostituzioni di <xref:System.Xaml.XamlType.LookupCollectionKind%2A> in un tipo XAML.
