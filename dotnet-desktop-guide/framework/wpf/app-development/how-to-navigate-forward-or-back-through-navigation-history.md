---
title: 'Procedura: navigare in avanti o indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967249"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="69116-102">Procedura: navigare in avanti o indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="69116-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="69116-103">Questo esempio illustra come spostarsi in secondo piano o tornare alle voci nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="69116-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69116-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="69116-104">Example</span></span>  
 <span data-ttu-id="69116-105">Il codice che viene eseguito dal contenuto negli host seguenti può spostarsi in diretta o indietro nella cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="69116-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="69116-106"><xref:System.Windows.Navigation.NavigationWindow> usando <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="69116-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="69116-107"><xref:System.Windows.Controls.Frame> usando <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="69116-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="69116-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="69116-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="69116-109">Prima di poter spostarsi in un secondo momento, è necessario verificare che siano presenti voci nella cronologia di navigazione in diretta controllando la proprietà **CanGoForward** .</span><span class="sxs-lookup"><span data-stu-id="69116-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="69116-110">Per spostarsi in una voce, chiamare il metodo **GoForward** .</span><span class="sxs-lookup"><span data-stu-id="69116-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="69116-111">Questo è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="69116-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="69116-112">Prima di poter spostarsi indietro di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione indietro controllando la proprietà **CanGoBack** .</span><span class="sxs-lookup"><span data-stu-id="69116-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="69116-113">Per spostarsi indietro di una voce, viene chiamato il metodo **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="69116-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="69116-114">Questo è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="69116-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="69116-115">**CanGoForward**, **GoForward**, **CanGoBack** e **GoBack** sono implementati da <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationService> .</span><span class="sxs-lookup"><span data-stu-id="69116-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69116-116">Se si chiama **GoForward** e non sono presenti voci nella cronologia di navigazione in diretta o se si chiama **GoBack** e non sono presenti voci nella cronologia di navigazione indietro, <xref:System.InvalidOperationException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="69116-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
