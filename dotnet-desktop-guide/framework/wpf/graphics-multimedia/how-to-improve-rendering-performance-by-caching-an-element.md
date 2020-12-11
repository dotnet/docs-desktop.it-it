---
title: 'Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 118e8b0cca52c44788c9d5b291d710f765e7af2a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965257"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="cc954-102">Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento</span><span class="sxs-lookup"><span data-stu-id="cc954-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="cc954-103">Utilizzare la <xref:System.Windows.Media.BitmapCache> classe per migliorare le prestazioni di rendering di un oggetto complesso <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="cc954-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="cc954-104">Per memorizzare nella cache un elemento, creare una nuova istanza della <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="cc954-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="cc954-105">È possibile riutilizzare un oggetto <xref:System.Windows.Media.BitmapCache> in modo efficiente in un oggetto <xref:System.Windows.Media.BitmapCacheBrush> .</span><span class="sxs-lookup"><span data-stu-id="cc954-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc954-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc954-106">Example</span></span>  
 <span data-ttu-id="cc954-107">Nell'esempio di codice seguente viene illustrato come creare un elemento complesso e memorizzarlo nella cache come bitmap, migliorando le prestazioni quando l'elemento viene animato.</span><span class="sxs-lookup"><span data-stu-id="cc954-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="cc954-108">L'elemento è un'area di disegno che include geometrie di forma con molti vertici.</span><span class="sxs-lookup"><span data-stu-id="cc954-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="cc954-109">Un oggetto <xref:System.Windows.Media.BitmapCache> con valori predefiniti viene assegnato all'oggetto <xref:System.Windows.UIElement.CacheMode%2A> dell'area di disegno e un'animazione mostra la scalabilità uniforme della bitmap memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc954-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="cc954-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc954-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="cc954-111">Procedura: Usare un elemento memorizzato nella cache come pennello</span><span class="sxs-lookup"><span data-stu-id="cc954-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
