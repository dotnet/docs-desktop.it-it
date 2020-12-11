---
title: 'Procedura: ruotare un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966889"
---
# <a name="how-to-rotate-an-object"></a>Procedura: ruotare un oggetto
Questo esempio spiega come ruotare un oggetto. Nell'esempio viene prima creato un oggetto <xref:System.Windows.Media.RotateTransform> e quindi ne viene specificato il valore <xref:System.Windows.Media.RotateTransform.Angle%2A> in gradi.  
  
 Nell'esempio seguente viene ruotato un <xref:System.Windows.Shapes.Polyline> oggetto 45 gradi sull'angolo superiore sinistro.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e di <xref:System.Windows.Media.RotateTransform> specificano il punto su cui l'oggetto viene ruotato. Il punto centrale viene espresso nello spazio delle coordinate dell'elemento trasformato. Per impostazione predefinita, la rotazione viene applicata a (0,0), ovvero l'angolo superiore sinistro dell'oggetto da trasformare.  
  
 L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> oggetto in senso orario di 45 gradi sul punto (25, 50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Nella figura seguente vengono illustrati i risultati dell'applicazione di un <xref:System.Windows.Media.Transform> ai due oggetti.  
  
 ![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Due oggetti che ruotano di 45 gradi da centri di rotazione diversi  
  
 Negli <xref:System.Windows.Shapes.Polyline> esempi precedenti è un oggetto <xref:System.Windows.UIElement> . Quando si applica un oggetto <xref:System.Windows.Media.Transform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un oggetto <xref:System.Windows.UIElement> , è possibile utilizzare la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà per specificare un'origine per ogni oggetto <xref:System.Windows.Media.Transform> che si applica all'elemento. Poiché la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà utilizza coordinate relative, è possibile applicare una trasformazione al centro dell'elemento anche se non si conoscono le relative dimensioni. Per ulteriori informazioni e per un esempio, vedere [specificare l'origine di una trasformazione utilizzando valori relativi](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
