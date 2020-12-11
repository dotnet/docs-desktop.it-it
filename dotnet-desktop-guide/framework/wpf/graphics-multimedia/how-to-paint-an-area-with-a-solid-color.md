---
title: "Procedura: disegnare un'area con un colore a tinta unita"
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964522"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="9650d-102">Procedura: disegnare un'area con un colore a tinta unita</span><span class="sxs-lookup"><span data-stu-id="9650d-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="9650d-103">Per disegnare un'area con un colore a tinta unita, è possibile usare un pennello di sistema predefinito, ad esempio <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A> , oppure è possibile creare un nuovo oggetto <xref:System.Windows.Media.SolidColorBrush> e descriverne il nome <xref:System.Windows.Media.SolidColorBrush.Color%2A> usando i valori alfa, rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="9650d-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="9650d-104">In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9650d-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="9650d-105">Negli esempi seguenti vengono usate ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.</span><span class="sxs-lookup"><span data-stu-id="9650d-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9650d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9650d-106">Example</span></span>  
 <span data-ttu-id="9650d-107">**Uso di un pennello predefinito**</span><span class="sxs-lookup"><span data-stu-id="9650d-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="9650d-108">Nell'esempio seguente viene usato il pennello predefinito <xref:System.Windows.Media.Brushes.Blue%2A> per disegnare un rettangolo blu.</span><span class="sxs-lookup"><span data-stu-id="9650d-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="9650d-109">**Uso della notazione esadecimale**</span><span class="sxs-lookup"><span data-stu-id="9650d-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="9650d-110">L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.</span><span class="sxs-lookup"><span data-stu-id="9650d-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="9650d-111">**Uso dei valori ARGB**</span><span class="sxs-lookup"><span data-stu-id="9650d-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="9650d-112">Nell'esempio successivo viene creato un oggetto <xref:System.Windows.Media.SolidColorBrush> e ne viene descritto l' <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzo dei valori ARGB per il colore blu.</span><span class="sxs-lookup"><span data-stu-id="9650d-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="9650d-113">Per altri modi di descrivere il colore, vedere la <xref:System.Windows.Media.Color> struttura.</span><span class="sxs-lookup"><span data-stu-id="9650d-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="9650d-114">**Argomenti correlati**</span><span class="sxs-lookup"><span data-stu-id="9650d-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="9650d-115">Per ulteriori informazioni su <xref:System.Windows.Media.SolidColorBrush> ed esempi aggiuntivi, vedere Cenni preliminari sul [disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="9650d-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="9650d-116">Questo esempio di codice fa parte di un esempio più ampio fornito per la <xref:System.Windows.Media.SolidColorBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="9650d-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="9650d-117">Per l'esempio completo, vedere [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli).</span><span class="sxs-lookup"><span data-stu-id="9650d-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9650d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9650d-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
