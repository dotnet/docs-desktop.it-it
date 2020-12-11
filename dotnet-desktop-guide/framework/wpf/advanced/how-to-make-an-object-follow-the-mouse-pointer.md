---
title: 'Procedura: fare in modo che un oggetto segua il puntatore del mouse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: f348586341d0fa5b6e1a5fe15ab8c3a75e369e64
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965611"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="821b7-102">Procedura: fare in modo che un oggetto segua il puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="821b7-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="821b7-103">Questo esempio Mostra come modificare le dimensioni di un oggetto quando il puntatore del mouse viene spostato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="821b7-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="821b7-104">Nell'esempio è incluso un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file che crea [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="821b7-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="821b7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="821b7-105">Example</span></span>  
 <span data-ttu-id="821b7-106">Il codice XAML seguente crea [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , che è costituito da un oggetto <xref:System.Windows.Shapes.Ellipse> all'interno di un oggetto <xref:System.Windows.Controls.StackPanel> , e connette il gestore eventi per l' <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="821b7-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="821b7-107">Il codice sottostante seguente crea il <xref:System.Windows.UIElement.MouseMove> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="821b7-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="821b7-108">Quando il puntatore del mouse viene spostato, l'altezza e la larghezza di <xref:System.Windows.Shapes.Ellipse> vengono aumentate e diminuite.</span><span class="sxs-lookup"><span data-stu-id="821b7-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="821b7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="821b7-109">See also</span></span>

- [<span data-ttu-id="821b7-110">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="821b7-110">Input Overview</span></span>](input-overview.md)
