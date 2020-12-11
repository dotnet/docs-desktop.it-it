---
title: 'Procedura: Applicare animazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964066"
---
# <a name="how-to-apply-animations-to-text"></a>Procedura: Applicare animazioni al testo
Le animazioni possono modificare la visualizzazione e l'aspetto del testo nell'applicazione. Negli esempi seguenti vengono usati tipi diversi di animazioni per influenzare la visualizzazione del testo in un <xref:System.Windows.Controls.TextBlock> controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la larghezza del blocco di testo. Il valore della larghezza varia dalla larghezza del blocco di testo a 0 per una durata pari a 10 secondi, quindi inverte i valori della larghezza e continua. Questo tipo di animazione crea un effetto a comparsa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per animare l'opacità del blocco di testo. Il valore dell'opacità varia da 1,0 a 0 per una durata pari a 5 secondi, quindi inverte i valori dell'opacità e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Il diagramma seguente illustra l'effetto del <xref:System.Windows.Controls.TextBlock> controllo che modifica l'opacità da `1.00` a `0.00` durante l'intervallo di 5 secondi definito da <xref:System.Windows.Media.Animation.Timeline.Duration%2A> .  
  
 ![Testo che modifica l'opacità da 1,00 a 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.ColorAnimation> per animare il colore di primo piano del blocco di testo. Il valore del colore di primo piano varia da un colore a un altro per una durata pari a 5 secondi, quindi inverte i valori del colore e continua.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> per ruotare il blocco di testo. Il blocco di testo esegue una rotazione completa per una durata pari a 20 secondi, quindi continua a ripetere la rotazione.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
