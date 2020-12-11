---
title: "Procedura: creare e utilizzare un'area di disegno"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c9ee49327b6490df094e84b4227ea0fb2e757c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966019"
---
# <a name="how-to-create-and-use-a-canvas"></a>Procedura: creare e utilizzare un'area di disegno
In questo esempio viene illustrato come creare e utilizzare un'istanza di <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono posizionati in modo esplicito due <xref:System.Windows.Controls.TextBlock> elementi usando i <xref:System.Windows.Controls.Canvas.SetTop%2A> <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodi e di <xref:System.Windows.Controls.Canvas> . Nell'esempio viene inoltre assegnato un <xref:System.Windows.Controls.Control.Background%2A> colore `LightSteelBlue` a <xref:System.Windows.Controls.Canvas> .  
  
> [!NOTE]
> Quando si utilizza [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] per posizionare <xref:System.Windows.Controls.TextBlock> gli elementi, utilizzare <xref:System.Windows.Controls.Canvas.Top%2A> le <xref:System.Windows.Controls.Canvas.Left%2A> proprietà e.  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure](canvas-how-to-topics.md)
