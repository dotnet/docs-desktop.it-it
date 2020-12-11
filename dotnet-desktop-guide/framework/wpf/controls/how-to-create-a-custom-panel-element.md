---
title: 'Procedura: creare un elemento Panel personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969466"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="59750-102">Procedura: creare un elemento Panel personalizzato</span><span class="sxs-lookup"><span data-stu-id="59750-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="59750-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="59750-103">Example</span></span>  
 <span data-ttu-id="59750-104">Questo esempio illustra come eseguire l'override del comportamento di layout predefinito dell' <xref:System.Windows.Controls.Panel> elemento e creare elementi di layout personalizzati derivati da <xref:System.Windows.Controls.Panel> .</span><span class="sxs-lookup"><span data-stu-id="59750-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="59750-105">Nell'esempio viene definito un semplice <xref:System.Windows.Controls.Panel> elemento personalizzato denominato `PlotPanel` , che posiziona gli elementi figlio in base a due coordinate x e y hardcoded.</span><span class="sxs-lookup"><span data-stu-id="59750-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="59750-106">In questo esempio, `x` e `y` sono entrambi impostati su `50` ; pertanto, tutti gli elementi figlio vengono posizionati in corrispondenza di tale posizione sugli assi x e y.</span><span class="sxs-lookup"><span data-stu-id="59750-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="59750-107">Per implementare <xref:System.Windows.Controls.Panel> comportamenti personalizzati, nell'esempio vengono utilizzati i <xref:System.Windows.FrameworkElement.MeasureOverride%2A> <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi e.</span><span class="sxs-lookup"><span data-stu-id="59750-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="59750-108">Ogni metodo restituisce i <xref:System.Windows.Size> dati necessari per posizionare ed eseguire il rendering degli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="59750-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="59750-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59750-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="59750-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="59750-110">Panels Overview</span></span>](panels-overview.md)
