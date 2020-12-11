---
title: 'Procedura: gestire un evento caricato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 7ca95e195792f8fb4789c481e84dda51f2910434
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963763"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="9f6c5-102">Procedura: gestire un evento caricato</span><span class="sxs-lookup"><span data-stu-id="9f6c5-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="9f6c5-103">Questo esempio illustra come gestire l' <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> evento e uno scenario appropriato per la gestione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="9f6c5-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="9f6c5-104">Il gestore crea un oggetto <xref:System.Windows.Controls.Button> quando viene caricata la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f6c5-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f6c5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f6c5-105">Example</span></span>  
 <span data-ttu-id="9f6c5-106">Nell'esempio seguente viene utilizzato [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] insieme a un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="9f6c5-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="9f6c5-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f6c5-107">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="9f6c5-108">Eventi di durata degli oggetti</span><span class="sxs-lookup"><span data-stu-id="9f6c5-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="9f6c5-109">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="9f6c5-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="9f6c5-110">Procedure</span><span class="sxs-lookup"><span data-stu-id="9f6c5-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
