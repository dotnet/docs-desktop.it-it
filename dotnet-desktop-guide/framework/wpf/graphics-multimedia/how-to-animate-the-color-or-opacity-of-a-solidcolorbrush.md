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
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="c6e0b-102">Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="c6e0b-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="c6e0b-103">Questo esempio illustra come animare <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> .</span><span class="sxs-lookup"><span data-stu-id="c6e0b-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6e0b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6e0b-104">Example</span></span>  
 <span data-ttu-id="c6e0b-105">Nell'esempio seguente vengono usate tre animazioni per animare <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> .</span><span class="sxs-lookup"><span data-stu-id="c6e0b-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="c6e0b-106">La prima animazione, a <xref:System.Windows.Media.Animation.ColorAnimation> , cambia il colore del pennello in <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse entra nel rettangolo.</span><span class="sxs-lookup"><span data-stu-id="c6e0b-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="c6e0b-107">L'animazione successiva, un'altra <xref:System.Windows.Media.Animation.ColorAnimation> , cambia il colore del pennello in <xref:System.Windows.Media.Colors.Orange%2A> quando il mouse lascia il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="c6e0b-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="c6e0b-108">L'animazione finale, a <xref:System.Windows.Media.Animation.DoubleAnimation> , modifica l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="c6e0b-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="c6e0b-109">Per un esempio più completo che illustra come animare tipi diversi di pennelli, vedere l' [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="c6e0b-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="c6e0b-110">Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c6e0b-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="c6e0b-111">Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="c6e0b-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="c6e0b-112">Tuttavia, quando si applica un'unica animazione nel codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="c6e0b-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="c6e0b-113">Per un esempio, vedere [animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="c6e0b-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e0b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6e0b-114">See also</span></span>

- [<span data-ttu-id="c6e0b-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="c6e0b-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c6e0b-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="c6e0b-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="c6e0b-117">Brushes Sample (Esempio di pennelli)</span><span class="sxs-lookup"><span data-stu-id="c6e0b-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
