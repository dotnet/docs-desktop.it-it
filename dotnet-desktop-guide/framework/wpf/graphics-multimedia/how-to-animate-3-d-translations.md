---
title: 'Procedura: animare le traduzioni 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960859"
---
# <a name="how-to-animate-3d-translations"></a>Procedura: animare le traduzioni 3D
In questo argomento viene illustrato come aggiungere un'animazione a una trasformazione di conversione impostata su un modello 3D.  
  
 Il codice seguente illustra l'applicazione di un <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto alla <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà di un oggetto <xref:System.Windows.Media.Media3D.GeometryModel3D> .  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà di questo <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto viene animata usando il codice riportato di seguito.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
