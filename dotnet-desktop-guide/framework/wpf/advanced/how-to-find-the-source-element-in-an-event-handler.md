---
title: "Procedura: cercare l'elemento di origine in un gestore eventi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967864"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="88ffe-102">Procedura: cercare l'elemento di origine in un gestore eventi</span><span class="sxs-lookup"><span data-stu-id="88ffe-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="88ffe-103">Questo esempio illustra come trovare l'elemento di origine in un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="88ffe-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88ffe-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="88ffe-104">Example</span></span>  
 <span data-ttu-id="88ffe-105">Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi dichiarato in un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="88ffe-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="88ffe-106">Quando un utente fa clic sul pulsante a cui è collegato il gestore, il gestore modifica il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="88ffe-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="88ffe-107">Il codice del gestore utilizza la <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà dei dati dell'evento indirizzato riportati negli argomenti dell'evento per modificare il <xref:System.Windows.FrameworkElement.Width%2A> valore della proprietà nell' <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.</span><span class="sxs-lookup"><span data-stu-id="88ffe-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="88ffe-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88ffe-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="88ffe-109">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="88ffe-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="88ffe-110">Procedure</span><span class="sxs-lookup"><span data-stu-id="88ffe-110">How-to Topics</span></span>](events-how-to-topics.md)
