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
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Funzione Activate (riferimenti alle API non gestite WPF)

Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.

Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.

## <a name="syntax"></a>Sintassi

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parametri

`pParameters`\
Puntatore ai parametri di attivazione della finestra.

`ppInner`\
Puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [.NET Framework requisiti di sistema](/dotnet/framework/get-started/system-requirements).

**DLL**

Nel .NET Framework 3,0 e 3,5: PresentationHostDLL.dll

In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll

**Versione .NET Framework:**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)
