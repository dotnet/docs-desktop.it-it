---
title: estensione di markup x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960985"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="fae15-102">estensione di markup x:Reference</span><span class="sxs-lookup"><span data-stu-id="fae15-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="fae15-103">Fa riferimento a un'istanza di dichiarata in un'altra posizione nel markup XAML.</span><span class="sxs-lookup"><span data-stu-id="fae15-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="fae15-104">Il riferimento si riferisce a un elemento `x:Name` .</span><span class="sxs-lookup"><span data-stu-id="fae15-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="fae15-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="fae15-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="fae15-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="fae15-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="fae15-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="fae15-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="fae15-108">`x:Name`Valore (o valore della <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> proprietà identificata dall'oggetto) dell'istanza a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="fae15-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fae15-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fae15-109">Remarks</span></span>

<span data-ttu-id="fae15-110">`x:Reference` fornisce supporto a livello di linguaggio XAML per un concetto di riferimento a un elemento che è stato altrimenti implementato in Framework specifici, ad esempio WPF.</span><span class="sxs-lookup"><span data-stu-id="fae15-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="fae15-111">x:Reference e WPF</span><span class="sxs-lookup"><span data-stu-id="fae15-111">x:Reference and WPF</span></span>

<span data-ttu-id="fae15-112">In WPF e XAML 2006, i riferimenti agli elementi vengono risolti dalla funzionalità a livello di Framework dell' <xref:System.Windows.Data.Binding.ElementName%2A> associazione.</span><span class="sxs-lookup"><span data-stu-id="fae15-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="fae15-113">Per la maggior parte delle applicazioni e degli scenari WPF, <xref:System.Windows.Data.Binding.ElementName%2A> è comunque necessario utilizzare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="fae15-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="fae15-114">Le eccezioni a questo materiale sussidiario generale potrebbero includere casi in cui è presente un contesto dei dati o altre considerazioni sull'ambito che rendono data binding impraticabile e in cui la compilazione del markup non è implicata.</span><span class="sxs-lookup"><span data-stu-id="fae15-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="fae15-115">`x:Reference` è un costrutto definito in XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="fae15-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="fae15-116">In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF.</span><span class="sxs-lookup"><span data-stu-id="fae15-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="fae15-117">Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="fae15-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
