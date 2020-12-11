---
title: 'Funzione Activate: informazioni di riferimento sulle API WPF non gestite'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: c97069613a96009d0b9bb84e55c37b29c2d3ea5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951912"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="ebd73-102">Funzione Activate (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="ebd73-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="ebd73-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="ebd73-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="ebd73-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ebd73-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebd73-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebd73-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="ebd73-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ebd73-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="ebd73-107">Puntatore ai parametri di attivazione della finestra.</span><span class="sxs-lookup"><span data-stu-id="ebd73-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="ebd73-108">Puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ebd73-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebd73-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebd73-109">Requirements</span></span>

<span data-ttu-id="ebd73-110">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).</span><span class="sxs-lookup"><span data-stu-id="ebd73-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>

<span data-ttu-id="ebd73-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="ebd73-111">**DLL:**</span></span>

<span data-ttu-id="ebd73-112">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="ebd73-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="ebd73-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="ebd73-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="ebd73-114">**Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd73-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ebd73-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebd73-115">See also</span></span>

- [<span data-ttu-id="ebd73-116">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="ebd73-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
