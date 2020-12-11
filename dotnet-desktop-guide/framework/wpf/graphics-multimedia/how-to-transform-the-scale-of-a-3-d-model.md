---
title: 'Procedura: trasformare la scala di un modello 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965557"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>Procedura: trasformare la scala di un modello 3D
Questo esempio illustra come ridimensionare un oggetto 3D. Per ridimensionare un oggetto 3D, usare <xref:System.Windows.Media.Media3D.ScaleTransform3D> . Le <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> proprietà, e <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> ridimensionano l'elemento in base al fattore specificato. Ad esempio, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valore di 1,5 estende un oggetto a 150% della larghezza originale. <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>Il valore 0,5 compatta l'altezza di un oggetto del 50%. Il codice seguente illustra l'uso di <xref:System.Windows.Media.Media3D.ScaleTransform3D> come trasformazione per un oggetto <xref:System.Windows.Media.Media3D.GeometryModel3D> .  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare le conversioni 3D](how-to-animate-3-d-translations.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
