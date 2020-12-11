---
title: 'Procedura: spostarsi indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967252"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="24aef-102">Procedura: spostarsi indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="24aef-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="24aef-103">Questo esempio illustra come passare alle voci nella cronologia di navigazione indietro.</span><span class="sxs-lookup"><span data-stu-id="24aef-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24aef-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="24aef-104">Example</span></span>  
 <span data-ttu-id="24aef-105">Il codice eseguito dal contenuto ospitato in un oggetto <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> utilizzando <xref:System.Windows.Navigation.NavigationService> o Internet Explorer può tornare alla cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="24aef-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="24aef-106">Per spostarsi indietro di una voce è necessario prima verificare che siano presenti voci nella cronologia di navigazione indietro, controllando la proprietà **CanGoBack** , prima di tornare indietro di una voce, chiamando il metodo **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="24aef-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="24aef-107">Questo è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="24aef-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="24aef-108">**CanGoBack** e **GoBack** sono implementati da <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationService> .</span><span class="sxs-lookup"><span data-stu-id="24aef-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24aef-109">Se si chiama **GoBack** e non sono presenti voci nella cronologia di navigazione indietro, <xref:System.InvalidOperationException> viene generato un oggetto.</span><span class="sxs-lookup"><span data-stu-id="24aef-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
