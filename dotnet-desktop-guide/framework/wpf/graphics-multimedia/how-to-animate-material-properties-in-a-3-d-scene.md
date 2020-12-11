---
title: 'Procedura: animare le proprietà del materiale in una scena 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961096"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>Procedura: animare le proprietà del materiale in una scena 3D
Questo esempio illustra come aggiungere un'animazione alla <xref:System.Windows.Media.Brush.Opacity%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.  
  
 Nell'esempio di codice seguente viene definito l' <xref:System.Windows.Media.LinearGradientBrush> oggetto utilizzato come <xref:System.Windows.Media.Media3D.Material> applicato all'oggetto 3D.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 La <xref:System.Windows.Media.Brush.Opacity%2A> proprietà di questo oggetto <xref:System.Windows.Media.LinearGradientBrush> viene animata usando l'esempio di codice seguente.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
