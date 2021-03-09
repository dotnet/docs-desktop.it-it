---
title: 'Procedura: creare un arco ellittico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 4963b671e07255053aef3661a0f7675ef6c5b69f
ms.sourcegitcommit: 754c22d76466a56133dd9a8006ad685fc1cd3d0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511645"
---
# <a name="how-to-create-an-elliptical-arc"></a>Procedura: creare un arco ellittico
Questo esempio illustra come creare un arco ellittico. Per creare un arco ellittico, usare le <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.PathFigure> classi, e <xref:System.Windows.Media.ArcSegment> .  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene disegnato un arco ellittico da (10.100) a (200.100). L'arco ha un <xref:System.Windows.Media.ArcSegment.Size%2A> valore di 100 di 50 pixel indipendenti dal dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> di 45 gradi, un' <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> impostazione di `true` e un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> di <xref:System.Windows.Media.SweepDirection.Counterclockwise> .  

 In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare la sintassi degli attributi per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  

 Si noti che questa sintassi di attributo crea effettivamente un oggetto <xref:System.Windows.Media.StreamGeometry> , una versione più leggera di un oggetto <xref:System.Windows.Media.PathGeometry> . Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] è anche possibile creare un arco ellittico usando in modo esplicito i tag Object. Il codice seguente equivale al markup precedente [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] .  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere l' [esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Vedi anche

- [Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
