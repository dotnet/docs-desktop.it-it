---
title: Direttiva x:Property
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: d4294b39ff262198f8082863d23eb6f4edbc7054
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960988"
---
# <a name="xproperty-directive"></a><span data-ttu-id="9e053-102">Direttiva x:Property</span><span class="sxs-lookup"><span data-stu-id="9e053-102">x:Property Directive</span></span>

<span data-ttu-id="9e053-103">Dichiara una proprietà XAML nel markup.</span><span class="sxs-lookup"><span data-stu-id="9e053-103">Declares a XAML property in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="9e053-104">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="9e053-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="9e053-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="9e053-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="9e053-106">Nome della classe sottostante o della classe parziale per la produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="9e053-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`propertyName`|<span data-ttu-id="9e053-107">Nome membro della proprietà da definire.</span><span class="sxs-lookup"><span data-stu-id="9e053-107">Member name of the property being defined.</span></span>|
|`propertyType`|<span data-ttu-id="9e053-108">Nome del tipo (o altro formato stringa, specifico del framework) che specifica il tipo di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e053-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e053-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9e053-109">Remarks</span></span>

<span data-ttu-id="9e053-110">Nell'implementazione dei servizi XAML .NET,.</span><span class="sxs-lookup"><span data-stu-id="9e053-110">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="9e053-111">`x:Property` non dispone di un supporto del tipo diretto, ma è supportato dalla classe <xref:System.Windows.Markup.PropertyDefinition>.</span><span class="sxs-lookup"><span data-stu-id="9e053-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="9e053-112">In un flusso del nodo XAML, un elemento `x:Property` viene rappresentato come membro denominato `Property`, dallo spazio dei nomi XAML del linguaggio XAML.</span><span class="sxs-lookup"><span data-stu-id="9e053-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="9e053-113">Il membro `Property` contiene gli attributi dichiarati dal markup.</span><span class="sxs-lookup"><span data-stu-id="9e053-113">The member `Property` hold attributes as declared by markup.</span></span>

<span data-ttu-id="9e053-114">Il significato di `Name` e `Type` non viene assegnato a livello di servizi XAML di .NET.</span><span class="sxs-lookup"><span data-stu-id="9e053-114">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="9e053-115">Vengono archiviati nel flusso del nodo XAML iniziale come valori di stringa, da interpretare in seguito in base alle regole che potrebbero essere imposte da framework specifici.</span><span class="sxs-lookup"><span data-stu-id="9e053-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="9e053-116">Il significato potrebbe allinearsi al significato di un nome XAML e di un tipo XAML o potrebbe essere valido solo in un sistema di tipi di supporto, a seconda dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="9e053-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="9e053-117">Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="9e053-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="9e053-118">Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="9e053-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="9e053-119">Tuttavia, il meccanismo per l'associazione di tipi e membri o per la produzione di definizioni di membri dinamici non è supportato a livello di servizi XAML di .NET.</span><span class="sxs-lookup"><span data-stu-id="9e053-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="9e053-120">Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML.</span><span class="sxs-lookup"><span data-stu-id="9e053-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="9e053-121">In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9e053-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="9e053-122">x:Property per Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="9e053-122">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="9e053-123">Per Windows Workflow Foundation, `x:Property` definisce i membri di un'attività personalizzata costituita interamente in XAML o i membri dinamici definiti da XAML per ActivityDesigner con code-behind.</span><span class="sxs-lookup"><span data-stu-id="9e053-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="9e053-124">`x:Class` deve essere specificato anche nell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="9e053-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="9e053-125">Questo non è un requisito a livello di servizi XAML di .NET, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e Windows Workflow Foundation XAML in generale.</span><span class="sxs-lookup"><span data-stu-id="9e053-125">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="9e053-126">Windows Workflow Foundation non usa il nome di tipo XAML puro come valore previsto per l' `x:Property` `Type` attributo e usa invece una convenzione che non è documentata qui.</span><span class="sxs-lookup"><span data-stu-id="9e053-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="9e053-127">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9e053-127">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
