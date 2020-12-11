---
title: 'Procedura: Usare un elemento memorizzato nella cache come pennello'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 78df242c7f00b69e36ea4ab6751f51509d9e2220
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968797"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="5126b-102">Procedura: Usare un elemento memorizzato nella cache come pennello</span><span class="sxs-lookup"><span data-stu-id="5126b-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="5126b-103">Utilizzare la <xref:System.Windows.Media.BitmapCacheBrush> classe per riutilizzare un elemento memorizzato nella cache in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="5126b-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="5126b-104">Per memorizzare nella cache un elemento, creare una nuova istanza della <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="5126b-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5126b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5126b-105">Example</span></span>  
 <span data-ttu-id="5126b-106">Nell'esempio di codice riportato di seguito viene illustrato come riutilizzare un elemento memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="5126b-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="5126b-107">L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="5126b-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="5126b-108">Il <xref:System.Windows.Controls.Image> controllo viene memorizzato nella cache come bitmap utilizzando la <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzata mediante l'assegnazione a <xref:System.Windows.Media.BitmapCacheBrush> .</span><span class="sxs-lookup"><span data-stu-id="5126b-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="5126b-109">Il pennello viene assegnato allo sfondo dei venti cinque pulsanti per mostrare un riutilizzo efficiente.</span><span class="sxs-lookup"><span data-stu-id="5126b-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="5126b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5126b-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="5126b-111">Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento</span><span class="sxs-lookup"><span data-stu-id="5126b-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
