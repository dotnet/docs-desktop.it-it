---
title: 'Procedura: applicare un disegno a un modello 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 794ca9a48bcec42c3eee4d8da143f3ae9d27fcf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966895"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>Procedura: applicare un disegno a un modello 3D

Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingBrush> come <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.

Il codice seguente definisce un oggetto <xref:System.Windows.Media.DrawingGroup> come contenuto di un oggetto <xref:System.Windows.Media.DrawingBrush> .  <xref:System.Windows.Media.DrawingBrush>Viene impostato come la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un piano 3D.

> [!NOTE]
> Spesso è consigliabile definire oggetti e valori complessi come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice. Per ulteriori informazioni, vedere [risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Esempio

Il codice seguente illustra l'intero esempio.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
