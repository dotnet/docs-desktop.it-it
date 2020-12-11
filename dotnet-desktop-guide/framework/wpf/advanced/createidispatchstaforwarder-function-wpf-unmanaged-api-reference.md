---
title: Funzione CreateIDispatchSTAForwarder-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7f60c53125eaaafe88b8777f3b560d5d1e083b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964138"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1b83d-102">Funzione CreateIDispatchSTAForwarder (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="1b83d-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1b83d-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="1b83d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1b83d-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di thread e finestre.</span><span class="sxs-lookup"><span data-stu-id="1b83d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b83d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b83d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b83d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b83d-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1b83d-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b83d-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="1b83d-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="1b83d-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="1b83d-109">Puntatore a un' `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1b83d-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="1b83d-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="1b83d-110">ppForwarder</span></span>  
 <span data-ttu-id="1b83d-111">Puntatore all'indirizzo di un' `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1b83d-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b83d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b83d-112">Requirements</span></span>  
 <span data-ttu-id="1b83d-113">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).</span><span class="sxs-lookup"><span data-stu-id="1b83d-113">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="1b83d-114">**DLL**</span><span class="sxs-lookup"><span data-stu-id="1b83d-114">**DLL:**</span></span>  
  
 <span data-ttu-id="1b83d-115">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1b83d-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1b83d-116">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1b83d-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1b83d-117">**Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b83d-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b83d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b83d-118">See also</span></span>

- [<span data-ttu-id="1b83d-119">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="1b83d-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
