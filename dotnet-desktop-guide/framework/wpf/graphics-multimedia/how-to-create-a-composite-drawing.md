---
title: 'Procedura: creare un disegno composto'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970003"
---
# <a name="how-to-create-a-composite-drawing"></a>Procedura: creare un disegno composto
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingGroup> per creare disegni complessi combinando più <xref:System.Windows.Media.Drawing> oggetti in un singolo disegno composto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.DrawingGroup> per creare un disegno composto <xref:System.Windows.Media.GeometryDrawing> dagli <xref:System.Windows.Media.ImageDrawing> oggetti e. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Disegno composito creato tramite l'oggetto DrawingGroup  
  
 Si noti il bordo grigio, che mostra i limiti del disegno.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 È possibile usare un oggetto <xref:System.Windows.Media.DrawingGroup> per applicare un'impostazione,,, <xref:System.Windows.Media.DrawingGroup.Transform%2A> <xref:System.Windows.Media.DrawingGroup.Opacity%2A> <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> ai disegni che contiene. Poiché un oggetto <xref:System.Windows.Media.DrawingGroup> è anche un <xref:System.Windows.Media.Drawing> , può contenere altri <xref:System.Windows.Media.DrawingGroup> oggetti.  
  
 L'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che usa <xref:System.Windows.Media.DrawingGroup> oggetti aggiuntivi per applicare gli effetti bitmap e una maschera di opacità ad alcuni dei relativi disegni. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto DrawingGroup con più disegni](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
Disegno composito con più oggetti DrawingGroup  
  
 Si noti il bordo grigio, che mostra i limiti del disegno.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Per altre informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
