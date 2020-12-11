---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: eb4b6a22a6f2f5de138ff3795dd32058f87cdb7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951270"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="a69dc-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="a69dc-102">IWpfHostSupport</span></span>

<span data-ttu-id="a69dc-103">Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] il contenuto tramite PresentationHost.exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e la PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="a69dc-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a69dc-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a69dc-104">Remarks</span></span>  

 <span data-ttu-id="a69dc-105">Le applicazioni Win32 quali i Web browser possono ospitare contenuto WPF, incluse le applicazioni browser XAML (XBAP) e il codice XAML separato.</span><span class="sxs-lookup"><span data-stu-id="a69dc-105">Win32 applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="a69dc-106">Per ospitare il contenuto WPF, le applicazioni Win32 creano un'istanza del [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="a69dc-106">To host WPF content, Win32 applications create an instance of the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span> <span data-ttu-id="a69dc-107">Per essere ospitata, WPF crea un'istanza di PresentationHost.exe, che fornisce il contenuto WPF ospitato all'host per la visualizzazione nel [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="a69dc-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
 <span data-ttu-id="a69dc-108">L'integrazione abilitata da `IWpfHostSupport` consente a PresentationHost.exe di:</span><span class="sxs-lookup"><span data-stu-id="a69dc-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="a69dc-109">Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="a69dc-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="a69dc-110">Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="a69dc-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="a69dc-111">Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a69dc-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a69dc-112">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="a69dc-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="a69dc-113">Membri</span><span class="sxs-lookup"><span data-stu-id="a69dc-113">Members</span></span>  
  
|<span data-ttu-id="a69dc-114">Membro</span><span class="sxs-lookup"><span data-stu-id="a69dc-114">Member</span></span>|<span data-ttu-id="a69dc-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a69dc-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a69dc-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="a69dc-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="a69dc-117">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="a69dc-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="a69dc-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="a69dc-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="a69dc-119">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a69dc-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="a69dc-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="a69dc-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="a69dc-121">Per impostazione predefinita, PresentationHost.exe fornisce le interfacce utente per lo stato della distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.</span><span class="sxs-lookup"><span data-stu-id="a69dc-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
