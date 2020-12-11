---
title: Attributo (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968581"
---
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="edaf5-102">Attributo (proprietà dinamica XElement)</span><span class="sxs-lookup"><span data-stu-id="edaf5-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="edaf5-103">Ottiene un indicizzatore usato per recuperare l'istanza dell'attributo che corrisponde al nome espanso specificato.</span><span class="sxs-lookup"><span data-stu-id="edaf5-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="edaf5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edaf5-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="edaf5-105">Valore proprietà/valore restituito</span><span class="sxs-lookup"><span data-stu-id="edaf5-105">Property value/return value</span></span>

<span data-ttu-id="edaf5-106">Indicizzatore del tipo `XAttribute Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="edaf5-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="edaf5-107">Questo indicizzatore accetta il nome espanso dell'attributo specificato e restituisce l'oggetto <xref:System.Xml.Linq.XAttribute> corrispondente o `null` se non esiste nessun attributo con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="edaf5-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="edaf5-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="edaf5-108">Remarks</span></span>

<span data-ttu-id="edaf5-109">Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="edaf5-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="edaf5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edaf5-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="edaf5-111">Proprietà dinamiche della classe XElement</span><span class="sxs-lookup"><span data-stu-id="edaf5-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="edaf5-112">Valore</span><span class="sxs-lookup"><span data-stu-id="edaf5-112">Value</span></span>](value-xattribute-dynamic-property.md)
