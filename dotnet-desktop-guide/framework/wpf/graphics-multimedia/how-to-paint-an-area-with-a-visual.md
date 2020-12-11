---
title: "Procedura: disegnare un'area con un oggetto Visual"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting [WPF]
- visuals [WPF], painting with
- brushes [WPF], painting with visuals
ms.assetid: 35f92996-1d03-4542-acc4-3469dcf09492
ms.openlocfilehash: 793a14f0d395a60bf73ca7dc173b82237a139f35
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968749"
---
# <a name="how-to-paint-an-area-with-a-visual"></a>Procedura: disegnare un'area con un oggetto Visual
Questo esempio illustra come usare la <xref:System.Windows.Media.VisualBrush> classe per disegnare un'area con un oggetto <xref:System.Windows.Media.Visual> .  
  
 Nell'esempio seguente vengono utilizzati diversi controlli e un pannello come sfondo di un rettangolo.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.VisualBrush> ed esempi aggiuntivi, vedere Cenni preliminari sul [disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md) .  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.VisualBrush> classe. Per l'esempio completo, vedere l' [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
