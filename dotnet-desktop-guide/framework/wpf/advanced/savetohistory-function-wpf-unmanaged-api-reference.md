---
title: Funzione SaveToHistory-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: f8cd39fce3f9bc41c315d4e19f95fd19d8bf9d93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967591"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>Funzione SaveToHistory (riferimenti alle API non gestite WPF)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pHistoryStream  
 Puntatore al flusso della cronologia.  
  
## <a name="requirements"></a>Requisiti  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).  
  
 **DLL**  
  
 Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)
