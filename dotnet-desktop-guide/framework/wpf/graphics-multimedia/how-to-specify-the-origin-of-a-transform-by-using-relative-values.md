---
title: "Procedura: specificare l'origine di una trasformazione utilizzando valori relativi"
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 48b3b0df8dab8516873495a996074eae57ffe00f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961276"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Procedura: specificare l'origine di una trasformazione utilizzando valori relativi
In questo esempio viene illustrato come utilizzare valori relativi per specificare l'origine di un oggetto <xref:System.Windows.UIElement.RenderTransform%2A> applicato a un oggetto <xref:System.Windows.FrameworkElement> .  
  
 Quando si ruota, ridimensiona o inclina un oggetto utilizzando <xref:System.Windows.FrameworkElement> la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, l'impostazione predefinita applica la trasformazione all'angolo superiore sinistro dell'elemento. Se si desidera ruotare, ridimensionare o inclinare dal centro dell'elemento, è possibile compensare impostando il centro della trasformazione sul centro dell'elemento. Tuttavia, questa soluzione prevede che si conoscano le dimensioni dell'elemento. Un modo più semplice per applicare una trasformazione al centro di un elemento consiste nell'impostare la relativa <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su (0,5, 0,5), anziché impostare un valore centrale sulla trasformazione stessa.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare di <xref:System.Windows.Controls.Button> 45 gradi in senso orario. Poiché l'esempio non specifica un centro, il pulsante ruota intorno al punto (0, 0), ovvero l'angolo superiore sinistro. <xref:System.Windows.Media.RotateTransform>Viene applicato alla <xref:System.Windows.UIElement.RenderTransform%2A> Proprietà.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato usando RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione in senso orario di 45 gradi usando la proprietà RenderTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Nell'esempio seguente viene anche usato un oggetto <xref:System.Windows.Media.RotateTransform> per ruotare di <xref:System.Windows.Controls.Button> 45 gradi in senso orario. in questo esempio l'oggetto <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante viene impostato su (0,5, 0,5). Di conseguenza, la rotazione viene applicata al centro del pulsante anziché all'angolo superiore sinistro.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato rispetto al proprio centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi usando la proprietà RenderTransform con RenderTransformOrigin del valore di (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Per ulteriori informazioni sulla trasformazione di <xref:System.Windows.FrameworkElement> oggetti, vedere [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
