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
# <a name="iwpfhostsupport"></a>IWpfHostSupport

Le applicazioni che ospitano [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] il contenuto tramite PresentationHost.exe implementano questa interfaccia per fornire un punto di integrazione tra l'host e la PresentationHost.exe.  
  
## <a name="remarks"></a>Osservazioni  

 Le applicazioni Win32 quali i Web browser possono ospitare contenuto WPF, incluse le applicazioni browser XAML (XBAP) e il codice XAML separato. Per ospitare il contenuto WPF, le applicazioni Win32 creano un'istanza del [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)). Per essere ospitata, WPF crea un'istanza di PresentationHost.exe, che fornisce il contenuto WPF ospitato all'host per la visualizzazione nel [controllo WebBrowser](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
 L'integrazione abilitata da `IWpfHostSupport` consente a PresentationHost.exe di:  
  
- Individuare e registrare con i dispositivi di input non elaborati (dispositivi di interfaccia umana) a cui è interessata l'applicazione host.  
  
- Ricevere messaggi di input dai dispositivi di input non elaborati registrati e inviare i messaggi appropriati all'applicazione host.  
  
- Eseguire una query sull'applicazione host per le interfacce utente di stato e di errore personalizzate.  
  
> [!NOTE]
> Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.|  
|[FilterInputMessage](filterinputmessage.md)|Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|Per impostazione predefinita, PresentationHost.exe fornisce le interfacce utente per lo stato della distribuzione e l'errore di distribuzione che vengono visualizzate quando si distribuisce il contenuto WPF.|
