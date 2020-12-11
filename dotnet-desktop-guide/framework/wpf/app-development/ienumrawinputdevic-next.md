---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951282"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="9484b-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="9484b-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="9484b-103">Enumera le `celt` strutture [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) successive nell'elenco dell'enumeratore, restituendo tali strutture `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched` .</span><span class="sxs-lookup"><span data-stu-id="9484b-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9484b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9484b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9484b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9484b-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="9484b-106">in Numero di strutture [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) restituite in `rgelt` .</span><span class="sxs-lookup"><span data-stu-id="9484b-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="9484b-107">[out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.</span><span class="sxs-lookup"><span data-stu-id="9484b-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="9484b-108">[out] Puntatore al numero di elementi effettivamente forniti in `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="9484b-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="9484b-109">Il chiamante può passare `NULL` se `rgelt` è uno.</span><span class="sxs-lookup"><span data-stu-id="9484b-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9484b-110">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9484b-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="9484b-111">HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="9484b-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
