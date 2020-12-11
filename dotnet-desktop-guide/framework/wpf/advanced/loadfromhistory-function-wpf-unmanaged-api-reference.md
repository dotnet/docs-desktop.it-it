---
title: Funzione LoadFromHistory-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: fa5851658fd21e222a277ea78ad8dcd53009bf17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968221"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="788ca-102">Funzione LoadFromHistory (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="788ca-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="788ca-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="788ca-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="788ca-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="788ca-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="788ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="788ca-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="788ca-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="788ca-106">Parameters</span></span>  
 <span data-ttu-id="788ca-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="788ca-107">pHistoryStream</span></span>  
 <span data-ttu-id="788ca-108">Puntatore a un flusso di informazioni sulla cronologia.</span><span class="sxs-lookup"><span data-stu-id="788ca-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="788ca-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="788ca-109">pBindCtx</span></span>  
 <span data-ttu-id="788ca-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="788ca-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788ca-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="788ca-111">Requirements</span></span>  
 <span data-ttu-id="788ca-112">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).</span><span class="sxs-lookup"><span data-stu-id="788ca-112">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="788ca-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="788ca-113">**DLL:**</span></span>  
  
 <span data-ttu-id="788ca-114">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="788ca-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="788ca-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="788ca-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="788ca-116">**Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788ca-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788ca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="788ca-117">See also</span></span>

- [<span data-ttu-id="788ca-118">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="788ca-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
