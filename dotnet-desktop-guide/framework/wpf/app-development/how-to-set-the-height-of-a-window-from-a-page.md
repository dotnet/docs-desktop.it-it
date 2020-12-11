---
title: "Procedura: impostare l'altezza di una finestra da una pagina"
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951311"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="f4f68-102">Procedura: impostare l'altezza di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="f4f68-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="f4f68-103">Questo esempio illustra come impostare l'altezza della finestra da un oggetto <xref:System.Windows.Controls.Page> .</span><span class="sxs-lookup"><span data-stu-id="f4f68-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4f68-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4f68-104">Example</span></span>  
 <span data-ttu-id="f4f68-105">Un oggetto <xref:System.Windows.Controls.Page> può impostare l'altezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowHeight%2A> .</span><span class="sxs-lookup"><span data-stu-id="f4f68-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="f4f68-106">Questa proprietà consente <xref:System.Windows.Controls.Page> a di non avere una conoscenza esplicita del tipo di finestra che la ospita.</span><span class="sxs-lookup"><span data-stu-id="f4f68-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4f68-107">Per impostare l'altezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowHeight%2A> , un oggetto <xref:System.Windows.Controls.Page> deve essere l'elemento figlio di una finestra.</span><span class="sxs-lookup"><span data-stu-id="f4f68-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
