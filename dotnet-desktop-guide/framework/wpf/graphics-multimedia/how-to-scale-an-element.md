---
title: 'Procedura: ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967015"
---
# <a name="how-to-scale-an-element"></a>Procedura: ridimensionare un elemento
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.  
  
 Usare le <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e per ridimensionare l'elemento in base al fattore specificato. Il valore 1,5, ad esempio, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> estende l'elemento al 150% della larghezza originale. <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>Il valore 0,5 compatta l'altezza di un elemento del 50%.  
  
 Usare le <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà e per specificare il punto centrale dell'operazione di ridimensionamento. Per impostazione predefinita, un oggetto <xref:System.Windows.Media.ScaleTransform> viene centrato al punto (0, 0), che corrisponde all'angolo superiore sinistro del rettangolo. Questo ha l'effetto di trasferire l'elemento e anche di renderlo più grande, perché quando si applica un <xref:System.Windows.Media.Transform> , si modifica lo spazio delle coordinate in cui si trova l'oggetto.  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.ScaleTransform> per raddoppiare le dimensioni di un 50 per 50 <xref:System.Windows.Shapes.Rectangle> . Il <xref:System.Windows.Media.ScaleTransform> valore di è 0 (impostazione predefinita) per <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> .  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In genere, si impostano <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto ridimensionato: ( <xref:System.Windows.FrameworkElement.Width%2A> /2, <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 Nell'esempio seguente viene illustrato un altro oggetto di <xref:System.Windows.Shapes.Rectangle> dimensioni raddoppiate. Tuttavia, il <xref:System.Windows.Media.ScaleTransform> valore di è 25 per <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> , che corrisponde al centro del rettangolo.  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Nella figura seguente viene illustrata la differenza tra le due <xref:System.Windows.Media.ScaleTransform> operazioni. La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.  
  
 ![Ridimensionamenti con raddoppiamento di valore con punti centrali diversi](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi  
  
 Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure](transformations-how-to-topics.md)
