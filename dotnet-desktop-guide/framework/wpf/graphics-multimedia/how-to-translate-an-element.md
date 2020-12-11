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
# <a name="how-to-translate-an-element"></a><span data-ttu-id="7343c-102">Procedura: convertire un elemento</span><span class="sxs-lookup"><span data-stu-id="7343c-102">How to: Translate an Element</span></span>
<span data-ttu-id="7343c-103">Questo esempio illustra come tradurre (spostare) un elemento usando un oggetto <xref:System.Windows.Media.TranslateTransform> .</span><span class="sxs-lookup"><span data-stu-id="7343c-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="7343c-104">La <xref:System.Windows.Media.TranslateTransform> classe è particolarmente utile per lo sposti di elementi all'interno di pannelli che non supportano il posizionamento assoluto.</span><span class="sxs-lookup"><span data-stu-id="7343c-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="7343c-105">Ad esempio, applicando un oggetto <xref:System.Windows.Media.TranslateTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un elemento, è possibile spostare un elemento in un oggetto <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="7343c-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="7343c-106">Utilizzare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di <xref:System.Windows.Media.TranslateTransform> per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse x.</span><span class="sxs-lookup"><span data-stu-id="7343c-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="7343c-107">Utilizzare la <xref:System.Windows.Media.TranslateTransform.Y%2A> proprietà per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse y.</span><span class="sxs-lookup"><span data-stu-id="7343c-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="7343c-108">Infine, applicare alla <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="7343c-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="7343c-109">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.TranslateTransform> per spostare un elemento 50 pixel a destra e 50 pixel in basso.</span><span class="sxs-lookup"><span data-stu-id="7343c-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7343c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7343c-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="7343c-111">Per l'esempio completo, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="7343c-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7343c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7343c-112">See also</span></span>

- [<span data-ttu-id="7343c-113">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="7343c-113">Transforms Overview</span></span>](transforms-overview.md)
