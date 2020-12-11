---
title: '{} Sequenza di escape-estensione di markup'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969613"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="5edb5-102">{} Sequenza di escape/estensione di markup</span><span class="sxs-lookup"><span data-stu-id="5edb5-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="5edb5-103">Fornisce la sequenza di escape XAML per i valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="5edb5-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="5edb5-104">La sequenza di escape consente di interpretare i valori successivi nell'attributo come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="5edb5-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="5edb5-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="5edb5-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="5edb5-106">Utilizzo della sintassi XAML per elementi proprietà</span><span class="sxs-lookup"><span data-stu-id="5edb5-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="5edb5-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="5edb5-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="5edb5-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="5edb5-108">*literalValue*</span></span>|<span data-ttu-id="5edb5-109">Stringa letterale che segue la sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="5edb5-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="5edb5-110">Questa stringa contiene in genere una parentesi graffa di apertura o di chiusura ({o}).</span><span class="sxs-lookup"><span data-stu-id="5edb5-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="5edb5-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5edb5-111">Remarks</span></span>

<span data-ttu-id="5edb5-112">Viene utilizzata la sequenza {} di escape () in modo che una parentesi graffa aperta ({) possa essere utilizzata come carattere letterale in XAML.</span><span class="sxs-lookup"><span data-stu-id="5edb5-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="5edb5-113">I reader XAML usano in genere la parentesi graffa aperta ({) per indicare il punto di ingresso di un'estensione di markup. Tuttavia, prima di tutto controllano il carattere successivo per determinare se si tratta di una parentesi graffa di chiusura (}).</span><span class="sxs-lookup"><span data-stu-id="5edb5-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="5edb5-114">Solo quando le due parentesi graffe ( {} ) sono adiacenti, sono considerate una sequenza di escape.</span><span class="sxs-lookup"><span data-stu-id="5edb5-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="5edb5-115">Se viene rilevata la sequenza di escape, il reader XAML deve elaborare il resto della stringa sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="5edb5-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="5edb5-116">Tuttavia, se la sequenza di escape viene applicata a un membro che dispone di un convertitore di tipi, la stringa potrebbe subire la conversione del tipo quando viene interpretata da un writer XAML.</span><span class="sxs-lookup"><span data-stu-id="5edb5-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="5edb5-117">La sequenza di escape non è un'estensione di markup e non è supportata da una classe.</span><span class="sxs-lookup"><span data-stu-id="5edb5-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="5edb5-118">Tuttavia, è una convenzione che i reader XAML (compresi i lettori XAML personalizzati) devono rispettare.</span><span class="sxs-lookup"><span data-stu-id="5edb5-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="5edb5-119">In questo modo non è possibile usare come sequenza di escape le virgolette (").</span><span class="sxs-lookup"><span data-stu-id="5edb5-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="5edb5-120">Se è necessario impostare una virgoletta come valore della proprietà per una proprietà non di contenuto, utilizzare la sintassi dell'elemento proprietà e inserire le virgolette come una stringa all'interno dell'elemento Property oppure utilizzare un'entità carattere XML.</span><span class="sxs-lookup"><span data-stu-id="5edb5-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="5edb5-121">Per una proprietà di contenuto, le virgolette possono essere l'intero contenuto.</span><span class="sxs-lookup"><span data-stu-id="5edb5-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="5edb5-122">La sequenza di escape ( {} ) è spesso obbligatoria quando si specifica un tipo XML che deve includere un qualificatore dello spazio dei nomi in una posizione in cui può essere visualizzata un'estensione di markup XAML.</span><span class="sxs-lookup"><span data-stu-id="5edb5-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="5edb5-123">Questo percorso include l'inizio di un valore di attributo XAML e in un'estensione di markup immediatamente dopo un segno di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="5edb5-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="5edb5-124">Nell'esempio seguente vengono illustrate le sequenze di escape per uno spazio dei nomi XML che viene visualizzato all'inizio di un valore di attributo XAML.</span><span class="sxs-lookup"><span data-stu-id="5edb5-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="5edb5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5edb5-125">See also</span></span>

- [<span data-ttu-id="5edb5-126">Convertitori di tipi ed estensioni di markup per XAML</span><span class="sxs-lookup"><span data-stu-id="5edb5-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="5edb5-127">Entità carattere XML e XAML</span><span class="sxs-lookup"><span data-stu-id="5edb5-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
