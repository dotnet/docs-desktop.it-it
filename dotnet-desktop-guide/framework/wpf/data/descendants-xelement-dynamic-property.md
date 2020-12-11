---
title: Discendenti (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951646"
---
# <a name="descendants-xelement-dynamic-property"></a><span data-ttu-id="3a19d-102">Discendenti (proprietà dinamica XElement)</span><span class="sxs-lookup"><span data-stu-id="3a19d-102">Descendants (XElement dynamic property)</span></span>

<span data-ttu-id="3a19d-103">Ottiene un indicizzatore usato per recuperare tutti gli elementi discendente dell'elemento corrente che corrispondono al nome espanso specificato.</span><span class="sxs-lookup"><span data-stu-id="3a19d-103">Gets an indexer used to retrieve all the descendant elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a19d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a19d-104">Syntax</span></span>

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="3a19d-105">Valore proprietà/valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a19d-105">Property value/return value</span></span>

<span data-ttu-id="3a19d-106">Indicizzatore del tipo `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="3a19d-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="3a19d-107">Questo indicizzatore accetta il nome espanso degli elementi discendente specificati e restituisce gli elementi figlio corrispondenti in una raccolta <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.</span><span class="sxs-lookup"><span data-stu-id="3a19d-107">This indexer takes the expanded name of the specified descendant elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a19d-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3a19d-108">Remarks</span></span>

<span data-ttu-id="3a19d-109">Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> della classe <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="3a19d-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="3a19d-110">Gli elementi della raccolta restituita sono in ordine del documento dell'origine XML.</span><span class="sxs-lookup"><span data-stu-id="3a19d-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="3a19d-111">Questa proprietà usa l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="3a19d-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a19d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a19d-112">See also</span></span>

- [<span data-ttu-id="3a19d-113">Proprietà dinamiche della classe XElement</span><span class="sxs-lookup"><span data-stu-id="3a19d-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="3a19d-114">Elementi</span><span class="sxs-lookup"><span data-stu-id="3a19d-114">Elements</span></span>](elements-xelement-dynamic-property.md)
