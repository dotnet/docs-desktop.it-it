---
title: Direttiva x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 2d795ad1caa766d21ea98e5a97c98304067cbef1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961078"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="18fc6-102">Direttiva x:ClassModifier</span><span class="sxs-lookup"><span data-stu-id="18fc6-102">x:ClassModifier Directive</span></span>

<span data-ttu-id="18fc6-103">Modifica il comportamento di compilazione XAML quando `x:Class` viene fornito anche.</span><span class="sxs-lookup"><span data-stu-id="18fc6-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="18fc6-104">In particolare, anziché creare un oggetto parziale `class` `Public` con livello di accesso (impostazione predefinita), l'oggetto fornito `x:Class` viene creato con un `NotPublic` livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="18fc6-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="18fc6-105">Questo comportamento influiscono sul livello di accesso per la classe negli assembly generati.</span><span class="sxs-lookup"><span data-stu-id="18fc6-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="18fc6-106">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="18fc6-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="18fc6-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="18fc6-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="18fc6-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="18fc6-108">*NotPublic*</span></span>|<span data-ttu-id="18fc6-109">La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e varia a seconda del linguaggio di programmazione code-behind usato.</span><span class="sxs-lookup"><span data-stu-id="18fc6-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="18fc6-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="18fc6-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="18fc6-111">Dependencies</span><span class="sxs-lookup"><span data-stu-id="18fc6-111">Dependencies</span></span>

<span data-ttu-id="18fc6-112">è necessario fornire anche [x:Class](xclass-directive.md) sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina.</span><span class="sxs-lookup"><span data-stu-id="18fc6-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="18fc6-113">Per ulteriori informazioni, vedere la [ \[ sezione MS-XAML \] 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="18fc6-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="18fc6-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="18fc6-114">Remarks</span></span>

<span data-ttu-id="18fc6-115">Il valore di `x:ClassModifier` nell'utilizzo dei servizi XAML .NET varia in base al linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="18fc6-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="18fc6-116">La stringa da usare dipende dal modo in cui ogni linguaggio implementa i <xref:System.CodeDom.Compiler.CodeDomProvider> convertitori di tipi che restituisce per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e se tale lingua fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="18fc6-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="18fc6-117">Per C#, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal` .</span><span class="sxs-lookup"><span data-stu-id="18fc6-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="18fc6-118">Per Microsoft Visual Basic .NET, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend` .</span><span class="sxs-lookup"><span data-stu-id="18fc6-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="18fc6-119">Per C++/CLI, non esistono destinazioni che supportano la compilazione di XAML. Pertanto, il valore da passare non è specificato.</span><span class="sxs-lookup"><span data-stu-id="18fc6-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="18fc6-120">È anche possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` in C#, `Public` in Visual Basic). Tuttavia, l'impostazione di <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> viene eseguita raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è già il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="18fc6-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="18fc6-121">Altri valori con restrizioni a livello di accesso del codice utente equivalente, ad esempio `private` in C#, non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e pertanto il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificatore ha lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="18fc6-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="18fc6-122">Note sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="18fc6-122">Security Notes</span></span>

<span data-ttu-id="18fc6-123">Il livello di accesso dichiarato in `x:ClassModifier` è ancora soggetto all'interpretazione da parte di framework specifici e alle relative funzionalità.</span><span class="sxs-lookup"><span data-stu-id="18fc6-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="18fc6-124">WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal` , se a tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack.</span><span class="sxs-lookup"><span data-stu-id="18fc6-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="18fc6-125">Come conseguenza di questo caso e potenzialmente altri come implementati da altri Framework, non si basano esclusivamente su `x:ClassModifier` per bloccare tutti i possibili tentativi di creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="18fc6-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="18fc6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18fc6-126">See also</span></span>

- [<span data-ttu-id="18fc6-127">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="18fc6-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="18fc6-128">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="18fc6-128">Code-Behind and XAML in WPF</span></span>](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="18fc6-129">Direttiva x:FieldModifier</span><span class="sxs-lookup"><span data-stu-id="18fc6-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="18fc6-130">Sicurezza (WPF)</span><span class="sxs-lookup"><span data-stu-id="18fc6-130">Security (WPF)</span></span>](../framework/wpf/security-wpf.md)
- [<span data-ttu-id="18fc6-131">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="18fc6-131">Types Migrated from WPF to System.Xaml</span></span>](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
