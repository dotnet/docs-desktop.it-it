---
title: 'Procedura: creare una scena 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968029"
---
# <a name="how-to-create-a-3d-scene"></a>Procedura: creare una scena 3D
Questo esempio illustra come creare un oggetto 3D simile a un foglio di carta Flat che è stato ruotato. <xref:System.Windows.Controls.Viewport3D>Per creare questa semplice scena 3D, viene usato un insieme ai componenti seguenti:  
  
- Viene creata una fotocamera usando un <xref:System.Windows.Media.Media3D.PerspectiveCamera> . La fotocamera specifica quale parte della scena 3D è visualizzabile.  
  
- Viene creata una mesh per specificare la forma dell'oggetto 3D (foglio di carta) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> .  
  
- Viene specificato un materiale da visualizzare sulla superficie dell'oggetto (sfumatura lineare in questo esempio) utilizzando la <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> proprietà di <xref:System.Windows.Media.Media3D.GeometryModel3D> .  
  
- Viene creata una luce per illuminare l'oggetto usando <xref:System.Windows.Media.Media3D.DirectionalLight> .  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra come creare una scena 3D in XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra come creare la stessa scena 3D nel codice procedurale.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della grafica 3D](3-d-graphics-overview.md)
