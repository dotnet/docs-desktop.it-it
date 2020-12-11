---
title: 'Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960808"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>Procedura: applicare materiale alla parte anteriore e posteriore di un oggetto 3D
Nell'esempio seguente viene illustrato come applicare un oggetto <xref:System.Windows.Media.Media3D.Material> alla parte anteriore e posteriore di un oggetto 3D e animare l'oggetto per visualizzare entrambi i lati dell'oggetto. La <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D> oggetto viene utilizzata per applicare un oggetto rosso <xref:System.Windows.Media.Brush> al lato anteriore dell'oggetto e la <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> viene utilizzata per applicare un blu <xref:System.Windows.Media.Brush> al lato posteriore dell'oggetto. Il codice seguente illustra l'applicazione dei materiali all'oggetto:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra l'intero esempio.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Animare le proprietà Material in una scena 3D](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Applicare EmissiveMaterial a un oggetto 3D](how-to-apply-emissive-material-to-a-3-d-object.md)
