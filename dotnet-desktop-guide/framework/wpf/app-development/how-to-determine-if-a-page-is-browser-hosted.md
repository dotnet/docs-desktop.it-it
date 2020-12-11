---
title: 'Procedura: determinare se una pagina è ospitata in un browser'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965335"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="45bc2-102">Procedura: determinare se una pagina è ospitata in un browser</span><span class="sxs-lookup"><span data-stu-id="45bc2-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="45bc2-103">In questo esempio viene illustrato come determinare se un oggetto <xref:System.Windows.Controls.Page> è ospitato in un browser.</span><span class="sxs-lookup"><span data-stu-id="45bc2-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45bc2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="45bc2-104">Example</span></span>  
 <span data-ttu-id="45bc2-105">Un <xref:System.Windows.Controls.Page> può essere indipendente dall'host e, di conseguenza, può essere caricato in diversi tipi di host, tra cui un <xref:System.Windows.Controls.Frame> , un <xref:System.Windows.Navigation.NavigationWindow> o un browser.</span><span class="sxs-lookup"><span data-stu-id="45bc2-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="45bc2-106">Questo problema può verificarsi quando si dispone di un assembly di libreria che contiene una o più pagine e a cui fa riferimento più applicazioni host autonome e visualizzabili (XBAP).</span><span class="sxs-lookup"><span data-stu-id="45bc2-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="45bc2-107">Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> per determinare se un oggetto <xref:System.Windows.Controls.Page> è ospitato in un browser.</span><span class="sxs-lookup"><span data-stu-id="45bc2-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="45bc2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bc2-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
