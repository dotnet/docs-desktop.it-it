---
title: "Procedura: aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964078"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Procedura: aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement
Per aggiungere un'animazione alle dimensioni di un oggetto <xref:System.Windows.FrameworkElement> , è possibile aggiungere un'animazione alle relative <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e o utilizzare un'animazione <xref:System.Windows.Media.ScaleTransform> .  
  
 Nell'esempio seguente vengono animate le dimensioni di due pulsanti usando questi due approcci. Un pulsante viene ridimensionato animando la relativa <xref:System.Windows.FrameworkElement.Width%2A> proprietà e un altro viene ridimensionato animando un oggetto <xref:System.Windows.Media.ScaleTransform> applicato alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> Proprietà. Ogni pulsante contiene testo. Inizialmente, il testo viene visualizzato lo stesso in entrambi i pulsanti, ma quando i pulsanti vengono ridimensionati, il testo nel secondo pulsante diventa distorto.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Quando si trasforma un elemento, vengono trasformati l'intero elemento e il relativo contenuto. Quando si modificano direttamente le dimensioni di un elemento, come nel caso del primo pulsante, il contenuto dell'elemento non viene ridimensionato, a meno che le dimensioni e la posizione dipendano dalla dimensione del rispettivo elemento padre.  
  
 L'animazione delle dimensioni di un elemento tramite l'applicazione di una trasformazione animata alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> proprietà garantisce prestazioni migliori rispetto a quelle animate <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> direttamente e, perché la <xref:System.Windows.UIElement.RenderTransform%2A> proprietà non attiva un passaggio di layout.  
  
 Per ulteriori informazioni sull'animazione delle proprietà, vedere [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md). Per ulteriori informazioni sulle trasformazioni, vedere [Cenni preliminari sulle trasformazioni](../graphics-multimedia/transforms-overview.md).
