---
title: 'Procedura: convertire un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965554"
---
# <a name="how-to-translate-an-element"></a>Procedura: convertire un elemento
Questo esempio illustra come tradurre (spostare) un elemento usando un oggetto <xref:System.Windows.Media.TranslateTransform> .  
  
 La <xref:System.Windows.Media.TranslateTransform> classe è particolarmente utile per lo sposti di elementi all'interno di pannelli che non supportano il posizionamento assoluto. Ad esempio, applicando un oggetto <xref:System.Windows.Media.TranslateTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un elemento, è possibile spostare un elemento in un oggetto <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel> .  
  
 Utilizzare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di <xref:System.Windows.Media.TranslateTransform> per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse x. Utilizzare la <xref:System.Windows.Media.TranslateTransform.Y%2A> proprietà per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse y. Infine, applicare alla <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.TranslateTransform> per spostare un elemento 50 pixel a destra e 50 pixel in basso.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
