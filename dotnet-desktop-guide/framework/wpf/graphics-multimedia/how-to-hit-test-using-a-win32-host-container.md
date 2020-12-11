---
title: 'Procedura: eseguire un hit test utilizzando un contenitore di host Win32'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a181b66eb527a0194bdc392c2b57c3e5822affb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967969"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="94e51-102">Procedura: eseguire un hit test utilizzando un contenitore di host Win32</span><span class="sxs-lookup"><span data-stu-id="94e51-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="94e51-103">È possibile creare oggetti visivi in una finestra Win32 fornendo un contenitore della finestra host per gli oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="94e51-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="94e51-104">Per fornire la gestione degli eventi per gli oggetti visivi contenuti, elaborare i messaggi passati al ciclo del filtro messaggi del contenitore della finestra host.</span><span class="sxs-lookup"><span data-stu-id="94e51-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="94e51-105">Per altre informazioni su come ospitare oggetti visivi in una finestra Win32, vedere [esercitazione: hosting di oggetti visivi in un'applicazione Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) .</span><span class="sxs-lookup"><span data-stu-id="94e51-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e51-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e51-106">Example</span></span>  
 <span data-ttu-id="94e51-107">Nel codice seguente viene illustrato come configurare i gestori di eventi del mouse per una finestra Win32 utilizzata come contenitore host per gli oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="94e51-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="94e51-108">Nell'esempio seguente viene illustrato come impostare un hit test in risposta a intercettare eventi del mouse specifici.</span><span class="sxs-lookup"><span data-stu-id="94e51-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="94e51-109">L' <xref:System.Windows.Interop.HwndSource> oggetto presenta [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] contenuto all'interno di una finestra Win32.</span><span class="sxs-lookup"><span data-stu-id="94e51-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="94e51-110">Il valore della <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà dell' <xref:System.Windows.Interop.HwndSource> oggetto rappresenta il nodo di primo livello nella gerarchia della struttura ad albero visuale.</span><span class="sxs-lookup"><span data-stu-id="94e51-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="94e51-111">Per l'esempio completo sugli oggetti hit testing con un contenitore host Win32, vedere [esempio di hit test con interoperatività Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span><span class="sxs-lookup"><span data-stu-id="94e51-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e51-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e51-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="94e51-113">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="94e51-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="94e51-114">Esercitazione: Hosting di oggetti visivi in un'applicazione Win32</span><span class="sxs-lookup"><span data-stu-id="94e51-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
