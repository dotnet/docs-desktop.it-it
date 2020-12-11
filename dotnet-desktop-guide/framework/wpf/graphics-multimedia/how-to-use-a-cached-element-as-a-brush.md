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
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Procedura: Usare un elemento memorizzato nella cache come pennello
Utilizzare la <xref:System.Windows.Media.BitmapCacheBrush> classe per riutilizzare un elemento memorizzato nella cache in modo efficiente. Per memorizzare nella cache un elemento, creare una nuova istanza della <xref:System.Windows.Media.BitmapCache> classe e assegnarla alla proprietà dell'elemento <xref:System.Windows.UIElement.CacheMode%2A> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come riutilizzare un elemento memorizzato nella cache. L'elemento memorizzato nella cache è un <xref:System.Windows.Controls.Image> controllo che visualizza un'immagine di grandi dimensioni. Il <xref:System.Windows.Controls.Image> controllo viene memorizzato nella cache come bitmap utilizzando la <xref:System.Windows.Media.BitmapCache> classe e la cache viene riutilizzata mediante l'assegnazione a <xref:System.Windows.Media.BitmapCacheBrush> . Il pennello viene assegnato allo sfondo dei venti cinque pulsanti per mostrare un riutilizzo efficiente.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Procedura: Migliorare le prestazioni di rendering memorizzando nella cache un elemento](how-to-improve-rendering-performance-by-caching-an-element.md)
