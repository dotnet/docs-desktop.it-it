---
title: Elemento (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951851"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="4686b-102">Elemento (proprietà dinamica XElement)</span><span class="sxs-lookup"><span data-stu-id="4686b-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="4686b-103">Ottiene un indicizzatore usato per recuperare l'istanza dell'elemento figlio che corrisponde al nome espanso specificato.</span><span class="sxs-lookup"><span data-stu-id="4686b-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="4686b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4686b-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="4686b-105">Valore proprietà/valore restituito</span><span class="sxs-lookup"><span data-stu-id="4686b-105">Property value/return value</span></span>

<span data-ttu-id="4686b-106">Indicizzatore del tipo `XElement Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="4686b-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="4686b-107">Questo indicizzatore accetta un parametro del nome espanso e restituisce l'oggetto <xref:System.Xml.Linq.XElement> corrispondente o `null` se non esiste nessun elemento con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4686b-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="4686b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4686b-108">Remarks</span></span>

<span data-ttu-id="4686b-109">Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XContainer.Element%2A> della classe <xref:System.Xml.Linq.XContainer?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4686b-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="4686b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4686b-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="4686b-111">Proprietà dinamiche della classe XElement</span><span class="sxs-lookup"><span data-stu-id="4686b-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="4686b-112">Elementi</span><span class="sxs-lookup"><span data-stu-id="4686b-112">Elements</span></span>](elements-xelement-dynamic-property.md)
