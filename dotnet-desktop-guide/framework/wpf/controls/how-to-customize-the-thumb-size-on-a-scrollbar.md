---
title: 'Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968629"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento
In questo argomento viene illustrato come impostare l'oggetto <xref:System.Windows.Controls.Primitives.Thumb> di un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> su una dimensione fissa e come specificare una dimensione minima per l'oggetto <xref:System.Windows.Controls.Primitives.Thumb> di un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> .  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione fissa. Nell'esempio viene impostata la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> proprietà di <xref:System.Windows.Controls.Primitives.Thumb> su <xref:System.Double.NaN> e viene impostata l'altezza di <xref:System.Windows.Controls.Primitives.Thumb> .  Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con una <xref:System.Windows.Controls.Primitives.Thumb> larghezza fissa, impostare la larghezza di <xref:System.Windows.Controls.Primitives.Thumb> .  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione minima. Nell'esempio viene impostato il valore di <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> . Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con una <xref:System.Windows.Controls.Primitives.Thumb> larghezza minima, impostare la <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> .  
  
## <a name="code"></a>Codice  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
