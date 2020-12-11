---
title: "Procedura: ottenere e impostare la finestra principale dell'applicazione"
description: Seguire questo esempio per ottenere e impostare la finestra principale dell'applicazione all'interno di Windows Presentation Foundation applicazione (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969178"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="97c83-103">Procedura: ottenere e impostare la finestra principale dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="97c83-103">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="97c83-104">Questo esempio illustra come ottenere e impostare la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97c83-104">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97c83-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="97c83-105">Example</span></span>  
 <span data-ttu-id="97c83-106">Il primo oggetto <xref:System.Windows.Window> di cui viene creata un'istanza all'interno di un'applicazione Windows Presentation Foundation (WPF) viene impostato automaticamente da <xref:System.Windows.Application> come finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97c83-106">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="97c83-107">Il primo oggetto <xref:System.Windows.Window> di cui creare un'istanza sarà probabilmente la finestra specificata come URI (Uniform Resource Identifier) di avvio (vedere <xref:System.Windows.Application.StartupUri%2A> ).</span><span class="sxs-lookup"><span data-stu-id="97c83-107">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="97c83-108"><xref:System.Windows.Window>È anche possibile creare un'istanza del primo utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="97c83-108">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="97c83-109">Un esempio è l'apertura di una finestra durante l'avvio dell'applicazione, come la seguente:</span><span class="sxs-lookup"><span data-stu-id="97c83-109">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="97c83-110">In alcuni casi, la prima istanza di <xref:System.Windows.Window> non è in realtà la finestra principale dell'applicazione, ad esempio una schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="97c83-110">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="97c83-111">In questo caso, è possibile specificare la finestra principale dell'applicazione usando il markup, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="97c83-111">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="97c83-112">Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale <xref:System.Windows.Application.MainWindow%2A> usando il codice seguente, come segue:</span><span class="sxs-lookup"><span data-stu-id="97c83-112">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
