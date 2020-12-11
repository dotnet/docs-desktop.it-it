---
title: 'Procedura: chiamare una funzione di pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 0370fe0bcbdf5105ae1b65bb90346663b2786a63
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966448"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="901ee-102">Procedura: chiamare una funzione di pagina</span><span class="sxs-lookup"><span data-stu-id="901ee-102">How to: Call a Page Function</span></span>
<span data-ttu-id="901ee-103">Questo esempio illustra come chiamare una funzione di pagina da una [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="901ee-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="901ee-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="901ee-104">Example</span></span>  
 <span data-ttu-id="901ee-105">È possibile passare a una funzione di pagina usando un URI (Uniform Resource Identifier), esattamente come è possibile quando si passa a una pagina.</span><span class="sxs-lookup"><span data-stu-id="901ee-105">You can navigate to a page function using a uniform resource identifier (URI), just as you can when you navigate to a page.</span></span> <span data-ttu-id="901ee-106">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="901ee-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="901ee-107">Se è necessario passare i dati alla funzione di pagina, è possibile crearne un'istanza e passare i dati impostando una proprietà.</span><span class="sxs-lookup"><span data-stu-id="901ee-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="901ee-108">In alternativa, come illustrato nell'esempio seguente, è possibile passare i dati usando un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="901ee-108">Or, as the following example shows, you can pass the data using a non-parameterless constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="901ee-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="901ee-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
