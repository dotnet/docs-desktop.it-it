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
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento
Utilizzare la <xref:System.Windows.Media.BitmapCache> classe per migliorare le prestazioni di rendering di un oggetto complesso <xref:System.Windows.UIElement> . Per memorizzare nella cache un elemento, creare una nuova istanza della <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> . È possibile riutilizzare un oggetto <xref:System.Windows.Media.BitmapCache> in modo efficiente in un oggetto <xref:System.Windows.Media.BitmapCacheBrush> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come creare un elemento complesso e memorizzarlo nella cache come bitmap, migliorando le prestazioni quando l'elemento viene animato. L'elemento è un'area di disegno che include geometrie di forma con molti vertici. Un oggetto <xref:System.Windows.Media.BitmapCache> con valori predefiniti viene assegnato all'oggetto <xref:System.Windows.UIElement.CacheMode%2A> dell'area di disegno e un'animazione mostra la scalabilità uniforme della bitmap memorizzata nella cache.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Procedura: Usare un elemento memorizzato nella cache come pennello](how-to-use-a-cached-element-as-a-brush.md)
