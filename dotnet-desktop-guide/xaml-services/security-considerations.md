---
title: Considerazioni sulla sicurezza in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969811"
---
# <a name="xaml-security-considerations"></a>Considerazioni sulla sicurezza in XAML

Questo articolo descrive le procedure consigliate per la sicurezza nelle applicazioni quando si usano XAML e l'API dei servizi XAML .NET.

## <a name="untrusted-xaml-in-applications"></a>XAML non attendibile nelle applicazioni

Nel senso più generale, XAML non attendibile è un'origine XAML che l'applicazione non include o emette in modo specifico.

Il codice XAML compilato in o archiviato come `resx` risorsa di tipo in un assembly trusted e firmato non è intrinsecamente non attendibile. È possibile considerare attendibile il codice XAML in quanto si considera attendibile l'assembly nel suo complesso. Nella maggior parte dei casi, si è interessati solo agli aspetti di attendibilità del codice XAML separato, ovvero un'origine XAML che viene caricata da un flusso o da un altro I/O. Il codice XAML separato non è un componente o una funzionalità specifica di un modello di applicazione con un'infrastruttura di distribuzione e creazione di pacchetti. Tuttavia, un assembly può implementare un comportamento che prevede il caricamento di XAML separato.

Per XAML non attendibile, è consigliabile considerarlo generalmente uguale a quello di codice non attendibile. Usare il sandboxing o altre metafore per impedire che XAML non attendibile acceda al codice attendibile.

La natura delle funzionalità XAML fornisce al codice XAML il diritto di creare oggetti e di impostarne le proprietà. Queste funzionalità includono anche l'accesso ai convertitori di tipi, il mapping e l'accesso agli assembly nel dominio dell'applicazione, l'uso di estensioni di markup, `x:Code` blocchi e così via.

Oltre alle funzionalità a livello di linguaggio, XAML viene usato per la definizione dell'interfaccia utente in molte tecnologie. Il caricamento di XAML non attendibile potrebbe significare il caricamento di un'interfaccia utente di spoofing dannoso.

## <a name="sharing-context-between-readers-and-writers"></a>Condivisione del contesto tra Reader e writer

L'architettura dei servizi XAML .NET per i reader XAML e i writer XAML spesso richiede la condivisione di un reader XAML in un writer XAML o di un contesto dello schema XAML condiviso. La condivisione di oggetti o contesti potrebbe essere necessaria se si sta scrivendo la logica del ciclo di nodi XAML o se si specifica un percorso di salvataggio personalizzato. Non condividere le istanze del reader XAML, il contesto dello schema XAML non predefinito o le impostazioni per le classi reader/writer XAML tra codice attendibile e non attendibile.

La maggior parte degli scenari e delle operazioni che interessano la scrittura di oggetti XAML per un supporto di tipo basato su CLR può utilizzare solo il contesto dello schema XAML predefinito. Il contesto dello schema XAML predefinito non include in modo esplicito le impostazioni che potrebbero compromettere l'attendibilità totale. È quindi possibile condividere il contesto tra componenti reader/writer XAML attendibili e non attendibili. Tuttavia, se si esegue questa operazione, è consigliabile mantenere tali reader e writer in <xref:System.AppDomain> ambiti distinti, con uno di essi specificamente intenzionato/sandbox per l'attendibilità parziale.

## <a name="xaml-namespaces-and-assembly-trust"></a>Spazi dei nomi XAML e trust tra assembly

La sintassi e la definizione di base non qualificate per il modo in cui XAML interpreta un mapping dello spazio dei nomi XAML personalizzato a un assembly non distingue tra un assembly attendibile e non attendibile caricato nel dominio applicazione. Per questo motivo, è tecnicamente possibile che un assembly non attendibile spoofing il mapping dello spazio dei nomi XAML previsto di un assembly attendibile e acquisisca le informazioni sulle proprietà e sugli oggetti dichiarati di un'origine XAML. Se si dispone di requisiti di sicurezza per evitare questa situazione, è necessario eseguire il mapping dello spazio dei nomi XAML desiderato utilizzando una delle tecniche seguenti:

- Usare un nome di assembly completo con nome sicuro in qualsiasi mapping dello spazio dei nomi XAML eseguito dal codice XAML dell'applicazione.

- Limitare il mapping degli assembly a un set fisso di assembly di riferimento, costruendo uno specifico <xref:System.Xaml.XamlSchemaContext> per i reader XAML e i writer di oggetti XAML. Vedere <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.

## <a name="xaml-type-mapping-and-type-system-access"></a>Mapping dei tipi XAML e accesso al sistema di tipi

XAML supporta il proprio sistema di tipi, che in molti casi è un peer per il modo in cui CLR implementa il sistema di tipi CLR di base. Tuttavia, per alcuni aspetti della consapevolezza dei tipi in cui si stanno prendendo decisioni di attendibilità su un tipo in base alle relative informazioni sul tipo, è necessario rinviare le informazioni sul tipo nei tipi di supporto CLR. Questo perché alcune delle funzionalità di Reporting specifiche del sistema di tipi XAML vengono lasciate aperte come metodi virtuali e pertanto non sono completamente sottoposte al controllo delle implementazioni dei servizi XAML di .NET originali. Questi punti di estendibilità sono disponibili perché il sistema di tipi XAML è estendibile, in modo da corrispondere all'estensibilità del codice XAML e alle possibili strategie alternative di mapping dei tipi rispetto all'implementazione supportata da CLR e al contesto dello schema XAML predefinito. Per ulteriori informazioni, vedere le note specifiche su diverse proprietà di <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember> .

## <a name="see-also"></a>Vedere anche

- <xref:System.Xaml.Permissions.XamlAccessLevel>
