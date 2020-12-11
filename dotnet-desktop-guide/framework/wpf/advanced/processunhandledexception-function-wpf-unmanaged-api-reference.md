---
title: Funzione ProcessUnhandledException-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 7de12e0d21a6add88ce602ea00b7f7b3aaf0c197
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966790"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1454c-102">Funzione ProcessUnhandledException (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="1454c-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1454c-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="1454c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1454c-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1454c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1454c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1454c-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="1454c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1454c-106">Parameters</span></span>  
 <span data-ttu-id="1454c-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="1454c-107">errorMsg</span></span>  
 <span data-ttu-id="1454c-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1454c-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1454c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1454c-109">Requirements</span></span>  
 <span data-ttu-id="1454c-110">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).</span><span class="sxs-lookup"><span data-stu-id="1454c-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="1454c-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="1454c-111">**DLL:**</span></span>  
  
 <span data-ttu-id="1454c-112">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1454c-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1454c-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1454c-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1454c-114">**Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1454c-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1454c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1454c-115">See also</span></span>

- [<span data-ttu-id="1454c-116">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="1454c-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
