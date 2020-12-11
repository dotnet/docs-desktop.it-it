---
title: 'Procedura: passare a una pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969796"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="bfb7e-102">Procedura: passare a una pagina</span><span class="sxs-lookup"><span data-stu-id="bfb7e-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="bfb7e-103">In questo esempio vengono illustrati diversi modi in cui una pagina può essere spostata da un oggetto <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="bfb7e-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfb7e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfb7e-104">Example</span></span>  
 <span data-ttu-id="bfb7e-105">Per <xref:System.Windows.Navigation.NavigationWindow> passare a una pagina, è possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="bfb7e-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="bfb7e-106">La proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="bfb7e-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="bfb7e-107">Metodo <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .</span><span class="sxs-lookup"><span data-stu-id="bfb7e-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> <span data-ttu-id="bfb7e-108">Gli URI (Uniform Resource Identifier) possono essere relativi o assoluti.</span><span class="sxs-lookup"><span data-stu-id="bfb7e-108">Uniform resource identifiers (URIs) can be either relative or absolute.</span></span> <span data-ttu-id="bfb7e-109">Per altre informazioni, vedere [URI di Pack in WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="bfb7e-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb7e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfb7e-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
