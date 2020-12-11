---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5aaa14cb3edfcba21814681dfaedd076274f6f66
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969067"
---
# <a name="xarguments-directive"></a><span data-ttu-id="6d979-102">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="6d979-102">x:Arguments Directive</span></span>

<span data-ttu-id="6d979-103">Pacchetti gli argomenti di costruzione per una dichiarazione di elemento oggetto costruttore senza parametri in XAML o per una dichiarazione di oggetto Metodo Factory.</span><span class="sxs-lookup"><span data-stu-id="6d979-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="6d979-104">Utilizzo di elementi XAML (costruttore senza parametri)</span><span class="sxs-lookup"><span data-stu-id="6d979-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6d979-105">Utilizzo di elementi XAML (metodo Factory)</span><span class="sxs-lookup"><span data-stu-id="6d979-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="6d979-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="6d979-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="6d979-107">Uno o più elementi oggetto che specificano gli argomenti da passare al costruttore o al metodo factory sottostante senza parametri.</span><span class="sxs-lookup"><span data-stu-id="6d979-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6d979-108">L'utilizzo tipico consiste nell'utilizzare il testo di inizializzazione negli elementi oggetto per specificare i valori effettivi degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="6d979-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6d979-109">Vedere la sezione esempi.</span><span class="sxs-lookup"><span data-stu-id="6d979-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6d979-110">L'ordine degli elementi è significativo.</span><span class="sxs-lookup"><span data-stu-id="6d979-110">The order of the elements is significant.</span></span> <span data-ttu-id="6d979-111">I tipi XAML in ordine devono corrispondere ai tipi e all'ordine del tipo del costruttore di supporto o dell'overload del metodo factory.</span><span class="sxs-lookup"><span data-stu-id="6d979-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="6d979-112">Nome del metodo factory che deve elaborare eventuali `x:Arguments` argomenti.</span><span class="sxs-lookup"><span data-stu-id="6d979-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="6d979-113">Dependencies</span><span class="sxs-lookup"><span data-stu-id="6d979-113">Dependencies</span></span>

<span data-ttu-id="6d979-114">`x:FactoryMethod` può modificare l'ambito e il comportamento in cui `x:Arguments` si applica.</span><span class="sxs-lookup"><span data-stu-id="6d979-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="6d979-115">Se non `x:FactoryMethod` è specificato, `x:Arguments` si applica alle firme alternative (non predefinite) dei costruttori di supporto.</span><span class="sxs-lookup"><span data-stu-id="6d979-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="6d979-116">Se `x:FactoryMethod` è specificato, `x:Arguments` si applica a un overload del metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="6d979-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d979-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6d979-117">Remarks</span></span>

<span data-ttu-id="6d979-118">XAML 2006 può supportare l'inizializzazione non predefinita tramite il testo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="6d979-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6d979-119">Tuttavia, l'applicazione pratica di una tecnica di costruzione del testo di inizializzazione è limitata.</span><span class="sxs-lookup"><span data-stu-id="6d979-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6d979-120">Il testo di inizializzazione viene considerato come una singola stringa di testo; viene pertanto aggiunta solo la funzionalità per l'inizializzazione di un singolo parametro, a meno che non venga definito un convertitore di tipi per il comportamento di costruzione che può analizzare elementi di informazioni personalizzate e delimitatori personalizzati dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="6d979-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6d979-121">Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente un convertitore di tipi predefinito nativo del parser XAML per la gestione di primitive diverse da una stringa vera.</span><span class="sxs-lookup"><span data-stu-id="6d979-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="6d979-122">L' `x:Arguments` utilizzo di XAML non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="6d979-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6d979-123">È più simile ad altre direttive, ad esempio `x:Code` quando l'elemento contrassegna un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="6d979-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6d979-124">In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento utilizzati dai parser XAML per determinare quale firma del metodo factory del costruttore specifico a cui `x:Arguments` si tenta di fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="6d979-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="6d979-125">`x:Arguments` per un elemento oggetto costruito deve precedere qualsiasi altro elemento di proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="6d979-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6d979-126">Gli elementi oggetto all'interno `x:Arguments` di possono includere attributi e stringhe di inizializzazione, come consentito dal tipo XAML e dal costruttore di supporto o dal metodo factory.</span><span class="sxs-lookup"><span data-stu-id="6d979-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6d979-127">Per l'oggetto o per gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano nello spazio dei nomi XAML predefinito facendo riferimento ai mapping di prefisso stabiliti.</span><span class="sxs-lookup"><span data-stu-id="6d979-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="6d979-128">I processori XAML utilizzano le linee guida seguenti per determinare la modalità di utilizzo degli argomenti specificati in `x:Arguments` per costruire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="6d979-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6d979-129">Se `x:FactoryMethod` si specifica, le informazioni vengono confrontate con l'oggetto specificato `x:FactoryMethod` (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può avere overload.</span><span class="sxs-lookup"><span data-stu-id="6d979-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6d979-130">Se `x:FactoryMethod` viene omesso, le informazioni vengono confrontate con il set di tutti gli overload del costruttore pubblico dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6d979-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6d979-131">La logica di elaborazione XAML confronta quindi il numero di parametri e seleziona l'overload con grado corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6d979-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6d979-132">Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi di parametri in base ai tipi XAML degli elementi oggetto forniti.</span><span class="sxs-lookup"><span data-stu-id="6d979-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6d979-133">Se è ancora presente più di una corrispondenza, il comportamento del processore XAML non è definito.</span><span class="sxs-lookup"><span data-stu-id="6d979-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6d979-134">Se `x:FactoryMethod` viene specificato un oggetto, ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6d979-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="6d979-135">Un utilizzo degli attributi XAML `<x:Arguments>string</x:Arguments>` è tecnicamente possibile.</span><span class="sxs-lookup"><span data-stu-id="6d979-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6d979-136">Tuttavia, non fornisce alcuna funzionalità oltre a quelle che potrebbero essere eseguite in altro modo tramite il testo di inizializzazione e i convertitori di tipi e l'utilizzo di questa sintassi non è l'intenzione di progettazione delle funzionalità del metodo factory XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="6d979-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="6d979-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="6d979-137">Examples</span></span>

<span data-ttu-id="6d979-138">Nell'esempio seguente viene illustrata una firma del costruttore senza parametri, quindi l'utilizzo di XAML di `x:Arguments` che accede a tale firma.</span><span class="sxs-lookup"><span data-stu-id="6d979-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="6d979-139">Nell'esempio seguente viene illustrata la firma di un metodo factory di destinazione, quindi l'utilizzo di XAML di `x:Arguments` che accede a tale firma.</span><span class="sxs-lookup"><span data-stu-id="6d979-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="6d979-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d979-140">See also</span></span>

- [<span data-ttu-id="6d979-141">Definizione di tipi personalizzati da usare con i servizi XAML .NET</span><span class="sxs-lookup"><span data-stu-id="6d979-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="6d979-142">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6d979-142">XAML Overview (WPF)</span></span>](../net/wpf/fundamentals/xaml.md)
