---
title: Estensione del markup x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: 88b32a59ca73a0e04582d873341567f42da013d3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966073"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="357d8-102">Estensione del markup x:Static</span><span class="sxs-lookup"><span data-stu-id="357d8-102">x:Static Markup Extension</span></span>

<span data-ttu-id="357d8-103">Fa riferimento a qualsiasi entità di codice statica per valore definita in un modo conforme a Common Language Specification (CLS).</span><span class="sxs-lookup"><span data-stu-id="357d8-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="357d8-104">È possibile utilizzare la proprietà statica a cui viene fatto riferimento per fornire il valore di una proprietà in XAML.</span><span class="sxs-lookup"><span data-stu-id="357d8-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="357d8-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="357d8-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="357d8-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="357d8-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="357d8-107">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="357d8-107">Optional.</span></span> <span data-ttu-id="357d8-108">Prefisso che fa riferimento a uno spazio dei nomi XAML non predefinito mappato.</span><span class="sxs-lookup"><span data-stu-id="357d8-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="357d8-109">`prefix` viene illustrato in modo esplicito nell'utilizzo perché raramente fanno riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito.</span><span class="sxs-lookup"><span data-stu-id="357d8-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="357d8-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="357d8-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="357d8-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="357d8-111">Required.</span></span> <span data-ttu-id="357d8-112">Nome del tipo che definisce il membro statico desiderato.</span><span class="sxs-lookup"><span data-stu-id="357d8-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="357d8-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="357d8-113">Required.</span></span> <span data-ttu-id="357d8-114">Nome del membro del valore statico desiderato, ovvero una costante, una proprietà statica, un campo o un valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="357d8-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="357d8-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="357d8-115">Remarks</span></span>

<span data-ttu-id="357d8-116">L'entità di codice a cui viene fatto riferimento deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="357d8-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="357d8-117">Una costante</span><span class="sxs-lookup"><span data-stu-id="357d8-117">A constant</span></span>
- <span data-ttu-id="357d8-118">Una proprietà statica</span><span class="sxs-lookup"><span data-stu-id="357d8-118">A static property</span></span>
- <span data-ttu-id="357d8-119">Un campo</span><span class="sxs-lookup"><span data-stu-id="357d8-119">A field</span></span>
- <span data-ttu-id="357d8-120">Valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="357d8-120">An enumeration value</span></span>

<span data-ttu-id="357d8-121">Se si specifica un'altra entità di codice, ad esempio una proprietà non statica, si verificherà un errore in fase di compilazione se il codice XAML è compilato o un'eccezione di analisi della fase di caricamento XAML.</span><span class="sxs-lookup"><span data-stu-id="357d8-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="357d8-122">È possibile fare `x:Static` riferimento a proprietà o campi statici che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente. Tuttavia, è necessario un mapping del prefisso.</span><span class="sxs-lookup"><span data-stu-id="357d8-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="357d8-123">Gli spazi dei nomi XAML sono quasi sempre definiti sull'elemento radice del documento XAML.</span><span class="sxs-lookup"><span data-stu-id="357d8-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="357d8-124">Le operazioni di ricerca per le proprietà statiche possono essere eseguite dai servizi XAML .NET e dai relativi reader XAML e writer XAML, quando sono in esecuzione con il contesto dello schema XAML predefinito.</span><span class="sxs-lookup"><span data-stu-id="357d8-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="357d8-125">Questo contesto dello schema XAML può utilizzare la reflection CLR per fornire i valori statici necessari per la costruzione di oggetti grafici.</span><span class="sxs-lookup"><span data-stu-id="357d8-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="357d8-126">L'oggetto `typeName` specificato è in realtà un nome di tipo XAML, non un nome di tipo CLR, anche se si tratta essenzialmente dello stesso nome quando si usa il contesto dello schema XAML predefinito o quando si usano tutti i Framework di implementazione XAML basati su CLR esistenti.</span><span class="sxs-lookup"><span data-stu-id="357d8-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="357d8-127">Prestare attenzione quando si fanno `x:Static` riferimento che non sono direttamente il tipo del valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="357d8-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="357d8-128">Nella sequenza di elaborazione XAML, i valori forniti da un'estensione di markup non richiamano la conversione di valori aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="357d8-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="357d8-129">Questo vale anche se il `x:Static` riferimento crea una stringa di testo e una conversione di valore per i valori di attributo basati su una stringa di testo si verifica in genere per quel membro specifico o per i valori dei membri del tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="357d8-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="357d8-130">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="357d8-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="357d8-131">Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.</span><span class="sxs-lookup"><span data-stu-id="357d8-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="357d8-132">Sono tecnicamente possibili altri due utilizzi di XAML.</span><span class="sxs-lookup"><span data-stu-id="357d8-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="357d8-133">Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:</span><span class="sxs-lookup"><span data-stu-id="357d8-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="357d8-134">Sintassi dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="357d8-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="357d8-135">Sintassi degli attributi con proprietà esplicita del membro per la stringa di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="357d8-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="357d8-136">Nell'implementazione dei servizi XAML .NET, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.Markup.StaticExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="357d8-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="357d8-137">`x:Static` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="357d8-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="357d8-138">Tutte le estensioni di markup in XAML usano i `{` `}` caratteri e nella relativa sintassi di attributo, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve fornire un valore.</span><span class="sxs-lookup"><span data-stu-id="357d8-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="357d8-139">Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="357d8-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="357d8-140">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="357d8-140">WPF Usage Notes</span></span>

<span data-ttu-id="357d8-141">Lo spazio dei nomi XAML predefinito utilizzato per la programmazione WPF non contiene molte proprietà statiche utili e la maggior parte delle proprietà statiche utili è supportata, ad esempio convertitori di tipi, che facilitano l'utilizzo senza che sia necessario `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="357d8-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="357d8-142">Per le proprietà statiche, è necessario eseguire il mapping di un prefisso per uno spazio dei nomi XAML se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="357d8-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="357d8-143">Si fa riferimento a un tipo esistente in WPF, ma che non fa parte dello spazio dei nomi XAML predefinito per WPF ( `http://schemas.microsoft.com/winfx/2006/xaml/presentation` ).</span><span class="sxs-lookup"><span data-stu-id="357d8-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="357d8-144">Si tratta di uno scenario abbastanza comune per l'utilizzo di `x:Static` .</span><span class="sxs-lookup"><span data-stu-id="357d8-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="357d8-145">È ad esempio possibile utilizzare un `x:Static` riferimento con un mapping dello spazio dei nomi XAML allo <xref:System> spazio dei nomi CLR e l'assembly mscorlib per fare riferimento alle proprietà statiche della <xref:System.Environment> classe.</span><span class="sxs-lookup"><span data-stu-id="357d8-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="357d8-146">Si fa riferimento a un tipo da un assembly personalizzato.</span><span class="sxs-lookup"><span data-stu-id="357d8-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="357d8-147">Si fa riferimento a un tipo esistente in un assembly WPF, ma tale tipo è incluso in uno spazio dei nomi CLR di cui non è stato eseguito il mapping per far parte dello spazio dei nomi XAML predefinito WPF.</span><span class="sxs-lookup"><span data-stu-id="357d8-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="357d8-148">Il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF viene eseguito dalle definizioni nei vari assembly WPF (per altre informazioni su questo concetto, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="357d8-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="357d8-149">Gli spazi dei nomi CLR non mappati possono esistere se lo spazio dei nomi CLR è costituito principalmente da definizioni di classe che in genere non sono destinate a XAML, ad esempio <xref:System.Windows.Threading> .</span><span class="sxs-lookup"><span data-stu-id="357d8-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="357d8-150">Per altre informazioni su come usare i prefissi e gli spazi dei nomi XAML per WPF, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="357d8-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="357d8-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="357d8-151">See also</span></span>

- [<span data-ttu-id="357d8-152">Estensione del markup x:Type</span><span class="sxs-lookup"><span data-stu-id="357d8-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="357d8-153">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="357d8-153">Types Migrated from WPF to System.Xaml</span></span>](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
