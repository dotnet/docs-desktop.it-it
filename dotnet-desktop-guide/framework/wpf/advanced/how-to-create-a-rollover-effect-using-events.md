---
title: 'Procedura: creare un effetto di attivazione utilizzando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d4587b7b116045af11702a99c841956434f96404
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967807"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="74a19-102">Procedura: creare un effetto di attivazione utilizzando gli eventi</span><span class="sxs-lookup"><span data-stu-id="74a19-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="74a19-103">Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="74a19-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="74a19-104">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="74a19-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74a19-105">Questo esempio illustra come usare gli eventi, ma la modalità consigliata per ottenere questo risultato consiste nell'usare un oggetto <xref:System.Windows.Trigger> in uno stile.</span><span class="sxs-lookup"><span data-stu-id="74a19-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="74a19-106">Per altre informazioni, vedere [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span><span class="sxs-lookup"><span data-stu-id="74a19-106">For more information, see [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74a19-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="74a19-107">Example</span></span>  
 <span data-ttu-id="74a19-108">Il codice XAML seguente crea l'interfaccia utente, che consiste <xref:System.Windows.Controls.Border> in un oggetto <xref:System.Windows.Controls.TextBlock> , e connette i <xref:System.Windows.Input.Mouse.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> gestori eventi e a <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="74a19-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="74a19-109">Il codice sottostante seguente consente di creare i <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> gestori eventi e.</span><span class="sxs-lookup"><span data-stu-id="74a19-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="74a19-110">Quando il puntatore del mouse entra <xref:System.Windows.Controls.Border> in, lo sfondo di <xref:System.Windows.Controls.Border> viene modificato in rosso.</span><span class="sxs-lookup"><span data-stu-id="74a19-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="74a19-111">Quando il puntatore del mouse esce dall'oggetto <xref:System.Windows.Controls.Border> , lo sfondo di <xref:System.Windows.Controls.Border> viene modificato di nuovo in bianco.</span><span class="sxs-lookup"><span data-stu-id="74a19-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
