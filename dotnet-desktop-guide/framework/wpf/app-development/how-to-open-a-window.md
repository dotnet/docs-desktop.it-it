---
title: 'Procedura: aprire una finestra'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969094"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="07f6d-102">Procedura: aprire una finestra</span><span class="sxs-lookup"><span data-stu-id="07f6d-102">How to: Open a Window</span></span>
<span data-ttu-id="07f6d-103">Questo esempio illustra come aprire una finestra.</span><span class="sxs-lookup"><span data-stu-id="07f6d-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07f6d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="07f6d-104">Example</span></span>  
 <span data-ttu-id="07f6d-105">Una finestra viene aperta creando un'istanza <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="07f6d-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="07f6d-106"><xref:System.Windows.Window.Show%2A> apre una finestra e restituisce immediatamente un valore senza attendere la chiusura della nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="07f6d-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="07f6d-107">Questo tipo di finestra è noto anche come finestra non *modale* e non limita l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="07f6d-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="07f6d-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="07f6d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="07f6d-109">La creazione <xref:System.Windows.Window> di istanze richiede l'autorizzazione per chiamare metodi nativi unsafe (vedere <xref:System.Windows.Window.%23ctor%2A> ).</span><span class="sxs-lookup"><span data-stu-id="07f6d-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
