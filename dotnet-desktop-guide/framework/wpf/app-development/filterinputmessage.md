---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1453946766e33843ae9e56f7a7f4dbf1678b81b5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965347"
---
# <a name="filterinputmessage"></a><span data-ttu-id="790aa-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="790aa-102">FilterInputMessage</span></span>
<span data-ttu-id="790aa-103">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="790aa-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="790aa-104">Syntax</span></span>  
  
```cpp  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
## <a name="parameters"></a><span data-ttu-id="790aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="790aa-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="790aa-106">[in] Messaggio WM_INPUT inviato alla finestra che sta ricevendo l'input non elaborato.</span><span class="sxs-lookup"><span data-stu-id="790aa-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="790aa-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="790aa-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="790aa-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="790aa-108">HRESULT:</span></span>  
  
 <span data-ttu-id="790aa-109">S_OK: il filtro non ha elaborato il messaggio e l'elaborazione può proseguire.</span><span class="sxs-lookup"><span data-stu-id="790aa-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="790aa-110">S_FALSE: il filtro ha elaborato questo messaggio e non viene eseguita alcuna ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="790aa-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="790aa-111">E_NOTIMPL: se viene restituito questo valore, [FilterInputMessage](filterinputmessage.md) non viene chiamato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="790aa-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="790aa-112">È possibile che venga restituito da un'applicazione host interessata solo a fornire interfacce utente personalizzate di stato ed errore a PresentationHost.exe e non a ricevere messaggi di input non elaborato da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="790aa-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="790aa-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="790aa-113">Remarks</span></span>  
 <span data-ttu-id="790aa-114">PresentationHost.exe è la destinazione di vari dispositivi di input non elaborato, tra cui tastiere, mouse e telecomandi.</span><span class="sxs-lookup"><span data-stu-id="790aa-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="790aa-115">In alcuni casi, il comportamento nell'applicazione host dipende dall'input che, in caso contrario, verrebbe usato da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="790aa-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="790aa-116">Ad esempio, la visualizzazione di specifici elementi dell'interfaccia utente da parte di un'applicazione host può dipendere dalla ricezione di determinati messaggi di input.</span><span class="sxs-lookup"><span data-stu-id="790aa-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="790aa-117">Per consentire all'applicazione host di ricevere i messaggi di input necessari per fornire questi comportamenti, PresentationHost.exe inoltri i messaggi di input non elaborati appropriati all'applicazione ospitata chiamando [FilterInputMessage](filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="790aa-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="790aa-118">L'applicazione ospitata riceve i messaggi di input non elaborati eseguendo la registrazione con il set di dispositivi di input non elaborati (Human Interface Device) restituiti da [GetRawInputDevices](getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="790aa-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790aa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="790aa-119">See also</span></span>

- [<span data-ttu-id="790aa-120">Messaggio WM_INPUT</span><span class="sxs-lookup"><span data-stu-id="790aa-120">WM_INPUT message</span></span>](/windows/desktop/inputdev/wm-input)
