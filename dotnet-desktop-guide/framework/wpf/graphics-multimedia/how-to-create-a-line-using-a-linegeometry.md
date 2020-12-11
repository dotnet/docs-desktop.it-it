---
title: 'Procedura: creare una riga utilizzando un oggetto LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967330"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Procedura: creare una riga utilizzando un oggetto LineGeometry
Questo esempio illustra come usare la <xref:System.Windows.Media.LineGeometry> classe per descrivere una riga. Un <xref:System.Windows.Media.LineGeometry> viene definito dai relativi punti iniziale e finale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare ed eseguire il rendering di un oggetto <xref:System.Windows.Media.LineGeometry> .  <xref:System.Windows.Shapes.Path>Viene usato un elemento per eseguire il rendering della riga.  Poiché una riga non ha un'area, l' <xref:System.Windows.Shapes.Path> oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> non è specificato, ma <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> vengono usate le proprietà e.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![Oggetto LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Un oggetto LineGeometry disegnato da (10,20) a (100,130)  
  
 Altre classi Geometry semplici includono <xref:System.Windows.Media.LineGeometry> e <xref:System.Windows.Media.EllipseGeometry> . Queste geometrie, così come quelle più complesse, possono essere create anche usando <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry> . Per altre informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
