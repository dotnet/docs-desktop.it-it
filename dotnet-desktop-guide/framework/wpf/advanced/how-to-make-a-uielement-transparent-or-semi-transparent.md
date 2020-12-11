---
title: 'Procedura: rendere trasparente o semitrasparente un oggetto UIElement'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963748"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Procedura: rendere trasparente o semitrasparente un oggetto UIElement
In questo esempio viene illustrato come rendere <xref:System.Windows.UIElement> trasparente o semitrasparente. Per rendere trasparente o semitrasparente un elemento, impostare la <xref:System.Windows.UIElement.Opacity%2A> Proprietà. Il valore `0.0` rende l'elemento completamente trasparente, mentre un valore `1.0` rende l'elemento completamente opaco. `0.5`Il valore rende opaco l'elemento 50% e così via. <xref:System.Windows.UIElement.Opacity%2A>Per impostazione predefinita, l'elemento è impostato su `1.0` .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.UIElement.Opacity%2A> di un pulsante su `0.25` , rendendola e il relativo contenuto, in questo caso il testo del pulsante, il 25% opaco.  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Se il contenuto di un elemento ha <xref:System.Windows.UIElement.Opacity%2A> impostazioni proprie, tali valori vengono moltiplicati per gli elementi che lo contengono <xref:System.Windows.UIElement.Opacity%2A> .  
  
 Nell'esempio seguente vengono impostati un pulsante <xref:System.Windows.UIElement.Opacity%2A> su `0.25` e l'oggetto <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Controls.Image> controllo contenuto nel pulsante in `0.5` . Di conseguenza, l'immagine viene visualizzata 12,5% opaca: 0,25 * 0,5 = 0,125.  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Un altro modo per controllare l'opacità di un elemento consiste nell'impostare l'opacità dell'oggetto <xref:System.Windows.Media.Brush> che disegna l'elemento. Questo approccio consente di modificare selettivamente l'opacità delle parti di un elemento e offre vantaggi in merito alle prestazioni rispetto all'utilizzo della proprietà dell'elemento <xref:System.Windows.UIElement.Opacity%2A> . Nell'esempio seguente viene impostato il <xref:System.Windows.Media.Brush.Opacity%2A> valore di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per disegnare l'oggetto del pulsante su <xref:System.Windows.Controls.Control.Background%2A> `0.25` . Di conseguenza, lo sfondo del pennello è opaco al 25%, ma il relativo contenuto (il testo del pulsante) rimane opaco al 100%.  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 È anche possibile controllare l'opacità dei singoli colori all'interno di un pennello. Per ulteriori informazioni sui colori e sui pennelli, vedere [Cenni preliminari sulla pittura con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Per un esempio che illustra come animare l'opacità di un elemento, vedere [animare l'opacità di un elemento o di un pennello](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
