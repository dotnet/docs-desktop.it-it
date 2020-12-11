---
title: 'Procedura: creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968005"
---
# <a name="how-to-create-a-combined-geometry"></a>Procedura: creare una geometria combinata
Questo esempio illustra come combinare le geometrie. Per combinare due geometrie, usare un <xref:System.Windows.Media.CombinedGeometry> oggetto. Impostare le <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> proprietà e con le due geometrie da combinare e impostare la <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà, che determina il modo in cui le geometrie verranno combinate insieme, a `Union` , `Intersect` , `Exclude` o `Xor` .  
  
 Per creare una geometria composta da due o più geometrie, usare un oggetto <xref:System.Windows.Media.GeometryGroup> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria di `Exclude` .  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Risultati della modalità di combinazione Exclude](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Esclusione geometria combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Intersect` .  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Risultati della modalità di combinazione Intersect](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Intersezione geometria combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Union` .  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Unione Geometry combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Xor` .  Sia <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> che <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
XOR Geometry combinato
