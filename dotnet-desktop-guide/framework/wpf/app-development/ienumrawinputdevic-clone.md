---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951290"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="6791b-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="6791b-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="6791b-103">Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="6791b-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6791b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6791b-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6791b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6791b-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="6791b-106">out Indirizzo della variabile di output che riceve il puntatore all'interfaccia [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) .</span><span class="sxs-lookup"><span data-stu-id="6791b-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="6791b-107">Se il metodo ha esito negativo, il valore di questa variabile di output non è definito.</span><span class="sxs-lookup"><span data-stu-id="6791b-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6791b-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6791b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="6791b-109">HRESULT: questo metodo supporta i valori restituiti standard E_INVALIDARG, E_OUTOFMEMORY e E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="6791b-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6791b-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6791b-110">Remarks</span></span>  
 <span data-ttu-id="6791b-111">Questo metodo consente di registrare un punto nella sequenza di enumerazione per tornare a tale punto in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6791b-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="6791b-112">Il chiamante deve rilasciare questo nuovo enumeratore separatamente dal primo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="6791b-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
