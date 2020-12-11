---
title: "Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush"
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961099"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush
Questo esempio illustra come animare <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono usate tre animazioni per animare <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> .  
  
- La prima animazione, a <xref:System.Windows.Media.Animation.ColorAnimation> , cambia il colore del pennello in <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse entra nel rettangolo.  
  
- L'animazione successiva, un'altra <xref:System.Windows.Media.Animation.ColorAnimation> , cambia il colore del pennello in <xref:System.Windows.Media.Colors.Orange%2A> quando il mouse lascia il rettangolo.  
  
- L'animazione finale, a <xref:System.Windows.Media.Animation.DoubleAnimation> , modifica l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Per un esempio più completo che illustra come animare tipi diversi di pennelli, vedere l' [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare le animazioni. Tuttavia, quando si applica un'unica animazione nel codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> . Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Brushes Sample (Esempio di pennelli)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
