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
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppenum`  
  
 out Indirizzo della variabile di output che riceve il puntatore all'interfaccia [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) . Se il metodo ha esito negativo, il valore di questa variabile di output non è definito.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: questo metodo supporta i valori restituiti standard E_INVALIDARG, E_OUTOFMEMORY e E_UNEXPECTED.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo consente di registrare un punto nella sequenza di enumerazione per tornare a tale punto in un secondo momento. Il chiamante deve rilasciare questo nuovo enumeratore separatamente dal primo enumeratore.
