---
title: "Procedura: animare l'opacità di un elemento o un pennello"
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 2f18861eb18f81b631245d1d933b7acb1b3e0e42
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968833"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Procedura: animare l'opacità di un elemento o un pennello
Per fare in modo che un elemento del Framework si dissolva e non sia più visualizzato, è possibile aggiungere un'animazione <xref:System.Windows.UIElement.Opacity%2A> alla relativa proprietà oppure è possibile aggiungere un'animazione alla <xref:System.Windows.Media.Brush.Opacity%2A> proprietà di <xref:System.Windows.Media.Brush> (o pennelli) utilizzata per disegnarla. L'animazione dell'opacità dell'elemento lo rende e i relativi elementi figlio si dissolve in visualizzazione, ma l'animazione del pennello utilizzato per disegnare l'elemento consente di rendere più selettiva la porzione dell'elemento. Ad esempio, è possibile animare l'opacità di un pennello usato per disegnare lo sfondo di un pulsante. In questo modo lo sfondo del pulsante potrebbe dissolversi in visualizzazione, lasciando il testo completamente opaco.  
  
> [!NOTE]
> L'animazione <xref:System.Windows.Media.Brush.Opacity%2A> di un oggetto <xref:System.Windows.Media.Brush> offre vantaggi in merito alle prestazioni rispetto all'animazione della <xref:System.Windows.UIElement.Opacity%2A> proprietà di un elemento.  
  
 Nell'esempio seguente, due pulsanti sono animati in modo da dissolverli e visualizzarli. L'opacità del primo <xref:System.Windows.Controls.Button> viene animata da `1.0` a `0.0` più <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi. Anche il secondo pulsante è animato, ma l'opacità dell'oggetto SolidColorBrush usato per disegnare <xref:System.Windows.Controls.Control.Background%2A> è animata anziché l'opacità dell'intero pulsante. Quando si esegue l'esempio, il primo pulsante dissolve completamente in entrata e in uscita, mentre solo lo sfondo del secondo pulsante si dissolve in entrata e in uscita. Il testo e il bordo rimangono completamente opachi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Il codice è stato omesso da questo esempio. Nell'esempio completo viene inoltre illustrato come animare l'opacità di un oggetto <xref:System.Windows.Media.Color> all'interno di un oggetto <xref:System.Windows.Media.LinearGradientBrush> .  Per l'esempio completo, vedere [animazione dell'esempio di opacità di un elemento](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
