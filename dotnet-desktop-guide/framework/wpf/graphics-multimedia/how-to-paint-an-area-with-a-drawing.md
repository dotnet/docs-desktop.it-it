---
title: "Procedura: inserire un disegno in un'area"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969853"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Procedura: inserire un disegno in un'area
Questo esempio spiega come inserire un disegno in un'area. Per disegnare un'area con un disegno, usare un oggetto <xref:System.Windows.Media.DrawingBrush> e uno o più <xref:System.Windows.Media.Drawing> oggetti.   Nell'esempio seguente viene usato un <xref:System.Windows.Media.DrawingBrush> oggetto per disegnare un oggetto con un disegno di due ellissi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 L'immagine seguente illustra l'output dell'esempio.  
  
 ![Output di DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")  
  
 Il centro della forma è bianco per i motivi descritti in     [controllare il riempimento di una forma composta](how-to-control-the-fill-of-a-composite-shape.md).  
  
 Impostando <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.TileBrush.Viewport%2A> le proprietà e di un oggetto <xref:System.Windows.Media.TileBrush.TileMode%2A> , è possibile creare un modello ripetuto. L'esempio seguente disegna un oggetto con un motivo creato da un disegno di due ellissi.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 Nella figura seguente viene illustrato l' <xref:System.Windows.Media.DrawingBrush> output affiancato.  
  
 ![Output affiancato di DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")  
  
 Per altre informazioni sulla creazione di pennelli, vedere disegnare [con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md). Per ulteriori informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).
