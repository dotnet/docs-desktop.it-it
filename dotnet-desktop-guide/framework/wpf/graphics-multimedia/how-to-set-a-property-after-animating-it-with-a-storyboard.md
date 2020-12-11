---
title: 'Procedura: impostare una proprietà dopo averla animata con uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965590"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Procedura: impostare una proprietà dopo averla animata con uno storyboard
In alcuni casi, potrebbe sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.Storyboard> viene usato un oggetto per animare il colore di un oggetto <xref:System.Windows.Media.SolidColorBrush> . Lo storyboard viene attivato quando si fa clic sul pulsante. L' <xref:System.Windows.Media.Animation.Timeline.Completed> evento viene gestito in modo che il programma riceva una notifica al <xref:System.Windows.Media.Animation.ColorAnimation> termine dell'operazione.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Esempio  
 Al termine dell' <xref:System.Windows.Media.Animation.ColorAnimation> operazione, il programma tenta di modificare il colore del pennello in blu.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Il codice precedente non sembra eseguire alcuna operazione: il pennello rimane giallo, che corrisponde al valore fornito dall'oggetto <xref:System.Windows.Media.Animation.ColorAnimation> che ha animato il pennello. Il valore della proprietà sottostante (valore di base) viene effettivamente modificato in blu. Tuttavia, il valore effettivo, o corrente, rimane giallo perché <xref:System.Windows.Media.Animation.ColorAnimation> sta ancora eseguendo l'override del valore di base. Se si desidera che il valore di base diventi di nuovo il valore effettivo, è necessario arrestare l'animazione dall'influire sulla proprietà. Esistono tre modi per eseguire questa operazione con le animazioni storyboard:  
  
- Impostare la proprietà dell'animazione <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> su <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
- Rimuovere l'intero storyboard.  
  
- Rimuovere l'animazione dalla singola proprietà.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Impostare la proprietà FillBehavior dell'animazione su Stop  
 Impostando <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> su <xref:System.Windows.Media.Animation.FillBehavior.Stop> , si indica all'animazione di arrestare l'effetto della proprietà di destinazione dopo che ha raggiunto la fine del periodo attivo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Rimuovere l'intero storyboard  
 Utilizzando un <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger o il <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> metodo, si indica alle animazioni dello storyboard di interrompere l'influire sulle proprietà di destinazione. La differenza tra questo approccio e l'impostazione della <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà è che è possibile rimuovere lo storyboard in qualsiasi momento, mentre la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà ha effetto solo quando l'animazione raggiunge la fine del periodo attivo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Rimuovere un'animazione da una singola proprietà  
 Un'altra tecnica per arrestare un'animazione dall'effetto di una proprietà consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo dell'oggetto a cui si sta aggiungendo un'animazione. Specificare la proprietà che viene animata come primo parametro e `null` come secondo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Questa tecnica funziona anche per le animazioni non Storyboard.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
