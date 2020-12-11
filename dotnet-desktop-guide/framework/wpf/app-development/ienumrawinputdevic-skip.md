---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967363"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="9c83a-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="9c83a-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="9c83a-103">Indica all'enumeratore di ignorare gli `celt` elementi successivi nell'enumerazione, in modo che la chiamata successiva a [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) non restituisca tali elementi.</span><span class="sxs-lookup"><span data-stu-id="9c83a-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c83a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c83a-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c83a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c83a-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="9c83a-106">in Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="9c83a-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9c83a-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9c83a-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="9c83a-108">HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="9c83a-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
