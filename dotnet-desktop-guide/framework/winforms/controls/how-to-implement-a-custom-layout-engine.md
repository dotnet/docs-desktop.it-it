---
title: 'Procedura: Implementare un motore di layout personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 8e5043e2b42b1e7449c6dab51691b6d57e28cd53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964348"
---
# <a name="how-to-implement-a-custom-layout-engine"></a><span data-ttu-id="4e183-102">Procedura: Implementare un motore di layout personalizzato</span><span class="sxs-lookup"><span data-stu-id="4e183-102">How to: Implement a Custom Layout Engine</span></span>
<span data-ttu-id="4e183-103">Nell'esempio di codice seguente viene illustrato come creare un motore di layout personalizzato che esegue un layout di flusso semplice.</span><span class="sxs-lookup"><span data-stu-id="4e183-103">The following code example demonstrates how to create a custom layout engine that performs a simple flow layout.</span></span> <span data-ttu-id="4e183-104">Implementa un controllo Panel denominato `DemoFlowPanel` , che esegue l'override della <xref:System.Windows.Forms.Control.LayoutEngine%2A> proprietà per fornire un'istanza della `DemoFlowLayout` classe.</span><span class="sxs-lookup"><span data-stu-id="4e183-104">It implements a panel control named `DemoFlowPanel`, which overrides the <xref:System.Windows.Forms.Control.LayoutEngine%2A> property to provide an instance of the `DemoFlowLayout` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e183-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e183-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4e183-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e183-106">See also</span></span>

- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
