---
title: 'Procedura: aggiornare una pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
ms.openlocfilehash: 71a71c91384a8905413358d023531afec23f2d41
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968956"
---
# <a name="how-to-refresh-a-page"></a><span data-ttu-id="ad3e1-102">Procedura: aggiornare una pagina</span><span class="sxs-lookup"><span data-stu-id="ad3e1-102">How to: Refresh a Page</span></span>
<span data-ttu-id="ad3e1-103">Questo esempio illustra come chiamare il <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> metodo per aggiornare il contenuto corrente in un oggetto <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="ad3e1-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> method to refresh the current content in a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3e1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad3e1-104">Example</span></span>  
 <span data-ttu-id="ad3e1-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> Aggiorna il contenuto corrente in un oggetto <xref:System.Windows.Navigation.NavigationWindow> per essere ricaricato dall'origine.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> refreshes the current content in a <xref:System.Windows.Navigation.NavigationWindow> to be reloaded from its source.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
