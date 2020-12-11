---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965344"
---
# <a name="getcustomui"></a>GetCustomUI
Chiamato da PresentationHost.exe per ottenere i messaggi di errore e di stato personalizzati dall'host, se implementati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzProgressAssemblyName`  
  
 out Puntatore all'assembly che contiene l'interfaccia utente di avanzamento fornita dall'host.  
  
 `pwzProgressClassName`  
  
 out Nome della classe che rappresenta l'interfaccia utente di avanzamento fornita dall'host, preferibilmente un file XAML con è il <xref:System.Windows.Controls.Page> relativo elemento di livello principale. Questa classe risiede nell'assembly specificato da `pwzProgressAssemblyName` .  
  
 `pwzErrorAssemblyName`  
  
 out Puntatore all'assembly che contiene l'interfaccia utente degli errori fornita dall'host.  
  
 `pwzErrorClassName`  
  
 out Nome della classe che rappresenta l'interfaccia utente degli errori fornita dall'host, preferibilmente un file XAML con è il <xref:System.Windows.Controls.Page> relativo elemento di livello principale. Questa classe risiede nell'assembly specificato da `pwzErrorAssemblyName` .  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: ignorato.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile che un'applicazione host disponga di un tema specifico per il quale le interfacce utente predefinite di PresentationHost.exe potrebbero non essere conformi a. In tal caso, l'applicazione host può implementare [GetCustomUI](getcustomui.md) per restituire le interfacce utente di stato ed errore per PresentationHost.exe. PresentationHost.exe chiamerà sempre [GetCustomUI](getcustomui.md) prima di utilizzare le interfacce utente predefinite.  
  
 Questa funzione viene chiamata una sola volta durante l'inizializzazione di PresentationHost.  
  
## <a name="see-also"></a>Vedere anche

- [IWpfHostSupport](iwpfhostsupport.md)
