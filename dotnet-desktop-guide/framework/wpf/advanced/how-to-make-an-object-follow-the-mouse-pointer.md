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
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Procedura: fare in modo che un oggetto segua il puntatore del mouse
Questo esempio Mostra come modificare le dimensioni di un oggetto quando il puntatore del mouse viene spostato sullo schermo.  
  
 Nell'esempio è incluso un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file che crea [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore eventi.  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente crea [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , che è costituito da un oggetto <xref:System.Windows.Shapes.Ellipse> all'interno di un oggetto <xref:System.Windows.Controls.StackPanel> , e connette il gestore eventi per l' <xref:System.Windows.UIElement.MouseMove> evento.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Il codice sottostante seguente crea il <xref:System.Windows.UIElement.MouseMove> gestore eventi.  Quando il puntatore del mouse viene spostato, l'altezza e la larghezza di <xref:System.Windows.Shapes.Ellipse> vengono aumentate e diminuite.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
