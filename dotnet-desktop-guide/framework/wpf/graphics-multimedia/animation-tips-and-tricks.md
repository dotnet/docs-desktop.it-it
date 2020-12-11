---
title: Suggerimenti sulle animazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: e0ff60e6119eec4838c98ed9e2e4081694285a8d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968836"
---
# <a name="animation-tips-and-tricks"></a>Suggerimenti sulle animazioni

Quando si lavora con le animazioni in WPF, sono disponibili numerosi suggerimenti e consigli che consentono di migliorare le prestazioni delle animazioni e di risparmiare.  
  
<a name="generalissuessection"></a>

## <a name="general-issues"></a>Problemi generali  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Blocco di una barra di scorrimento o di un dispositivo di scorrimento se si anima la relativa posizione  

 Se si anima la posizione di una barra di scorrimento o di un dispositivo di scorrimento usando un'animazione con un <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> valore di (valore predefinito), l'utente non sarà più in grado di spostare la barra di scorrimento o il dispositivo di scorrimento. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà di destinazione è ancora in corso. Per arrestare l'override del valore corrente della proprietà da parte dell'animazione, rimuoverla o assegnarla a <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop> . Per ulteriori informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Animazione dell'output di un'animazione senza alcun effetto  

 Non è possibile animare un oggetto che rappresenta l'output di un'altra animazione. Se ad esempio si usa un oggetto <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> per animare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un oggetto <xref:System.Windows.Shapes.Rectangle> da un oggetto <xref:System.Windows.Media.RadialGradientBrush> a un oggetto <xref:System.Windows.Media.SolidColorBrush> , non è possibile aggiungere un'animazione ad alcuna proprietà di <xref:System.Windows.Media.RadialGradientBrush> o <xref:System.Windows.Media.SolidColorBrush> .  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Impossibile modificare il valore di una proprietà dopo averla animata  

 In alcuni casi può sembrare che non sia possibile modificare il valore di una proprietà dopo che è stata animata, anche dopo il termine dell'animazione. Ciò è dovuto al fatto che, anche se l'animazione è terminata, l'override del valore di base della proprietà è ancora in corso. Per arrestare l'override del valore corrente della proprietà da parte dell'animazione, rimuoverla o assegnarla a <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop> . Per ulteriori informazioni e un esempio, vedere [impostare una proprietà dopo averla animata con uno storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Modifica di una sequenza temporale senza alcun effetto  

 Sebbene la maggior parte delle <xref:System.Windows.Media.Animation.Timeline> proprietà sia animata e possa essere associata ai dati, la modifica dei valori delle proprietà di un oggetto attivo <xref:System.Windows.Media.Animation.Timeline> sembra non avere alcun effetto. Questo perché, quando un <xref:System.Windows.Media.Animation.Timeline> viene avviato, il sistema di temporizzazione crea una copia di <xref:System.Windows.Media.Animation.Timeline> e la utilizza per creare un <xref:System.Windows.Media.Animation.Clock> oggetto. La modifica dell'originale non ha alcun effetto sulla copia del sistema.  
  
 Affinché un oggetto <xref:System.Windows.Media.Animation.Timeline> rifletta le modifiche, è necessario rigenerare il relativo clock e usarlo per sostituire il Clock creato in precedenza. Gli orologi non vengono rigenerati automaticamente. Di seguito vengono indicate diverse modalità per applicare le modifiche alla sequenza temporale:  
  
- Se la sequenza temporale è o appartiene a un oggetto <xref:System.Windows.Media.Animation.Storyboard> , è possibile fare in modo che rifletta le modifiche riapplicando il relativo storyboard usando un <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo o. Come effetto collaterale, l'animazione viene riavviata. Nel codice è possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo per far tornare lo storyboard alla posizione precedente.  
  
- Se un'animazione è stata applicata direttamente a una proprietà usando il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo, chiamare di <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nuovo il metodo e passargli l'animazione che è stata modificata.  
  
- Se si lavora direttamente a livello di orologio, creare e applicare un nuovo set di orologi e usarli per sostituire il set di orologi generati in precedenza.  
  
 Per altre informazioni sulle sequenze temporali e sugli orologi, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>Funzionamento imprevisto di FillBehavior.Stop  

 In alcuni casi, l'impostazione della <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà su <xref:System.Windows.Media.Animation.FillBehavior.Stop> sembra non avere alcun effetto, ad esempio quando un'animazione passa a un'altra, perché ha un' <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> impostazione di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> .  
  
 Nell'esempio seguente vengono creati un oggetto <xref:System.Windows.Controls.Canvas> , un oggetto <xref:System.Windows.Shapes.Rectangle> e un oggetto <xref:System.Windows.Media.TranslateTransform> . Il <xref:System.Windows.Media.TranslateTransform> viene animato per spostare l'oggetto <xref:System.Windows.Shapes.Rectangle> intorno a <xref:System.Windows.Controls.Canvas> .  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Negli esempi di questa sezione vengono usati gli oggetti precedenti per illustrare diversi casi in cui la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà non si comporta come previsto.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" e HandoffBehavior con animazioni multiple  

 Talvolta sembra che un'animazione ignori la relativa <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà quando viene sostituita da una seconda animazione. Usare l'esempio seguente, che crea due <xref:System.Windows.Media.Animation.Storyboard> oggetti e li usa per animare lo stesso oggetto <xref:System.Windows.Media.TranslateTransform> illustrato nell'esempio precedente.  
  
 Il primo <xref:System.Windows.Media.Animation.Storyboard> , `B1` , anima la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di <xref:System.Windows.Media.TranslateTransform> da 0 a 350, che sposta il rettangolo 350 pixel a destra. Quando l'animazione raggiunge la fine della durata e interrompe la riproduzione, la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà viene ripristinata sul valore originale 0. Il rettangolo di conseguenza si sposta a destra di 350 pixel e quindi torna alla posizione originale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Il secondo <xref:System.Windows.Media.Animation.Storyboard> , `B2` , aggiunge anche un'animazione alla <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà dello stesso oggetto <xref:System.Windows.Media.TranslateTransform> . Poiché <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> è impostata solo la proprietà dell'animazione in questo oggetto <xref:System.Windows.Media.Animation.Storyboard> , l'animazione usa il valore corrente della proprietà a cui viene aggiunta un'animazione come valore iniziale.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Se si fa clic sul secondo pulsante mentre il primo <xref:System.Windows.Media.Animation.Storyboard> è in riproduzione, è possibile che si verifichi il comportamento seguente:  
  
1. Il primo storyboard termina e invia nuovamente il rettangolo alla sua posizione originale, perché l'animazione ha un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> di <xref:System.Windows.Media.Animation.FillBehavior.Stop> .  
  
2. Il secondo storyboard viene applicato e viene animato dalla posizione corrente, da 0 a 500.  
  
 **Questa situazioni non è quella che si verifica.** Il rettangolo infatti non torna alla posizione originale ma continua a spostarsi a destra. Ciò accade perché la seconda animazione usa il valore corrente della prima animazione come valore iniziale e viene eseguita da tale valore fino a 500. Quando la seconda animazione sostituisce la prima perché <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> viene usato, la <xref:System.Windows.Media.Animation.FillBehavior> della prima animazione non è rilevante.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior ed evento Completed  

 Negli esempi successivi viene illustrato un altro scenario in cui <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> sembra non avere alcun effetto. Anche in questo caso, nell'esempio viene usato uno storyboard per aggiungere un'animazione alla <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di <xref:System.Windows.Media.TranslateTransform> da 0 a 350. Questa volta, tuttavia, l'esempio viene registrato per l' <xref:System.Windows.Media.Animation.Timeline.Completed> evento.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Il <xref:System.Windows.Media.Animation.Timeline.Completed> gestore eventi avvia un altro oggetto <xref:System.Windows.Media.Animation.Storyboard> che aggiunge un'animazione alla stessa proprietà dal relativo valore corrente a 500.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Di seguito è riportato il markup che definisce il secondo <xref:System.Windows.Media.Animation.Storyboard> come risorsa.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Quando si esegue <xref:System.Windows.Media.Animation.Storyboard> , si potrebbe prevedere che la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà dell'oggetto venga <xref:System.Windows.Media.TranslateTransform> animata da 0 a 350, quindi ripristinare 0 dopo il completamento (poiché dispone <xref:System.Windows.Media.Animation.FillBehavior> di un'impostazione di <xref:System.Windows.Media.Animation.FillBehavior.Stop> ), quindi aggiungere un'animazione da 0 a 500. Al contrario, l'oggetto <xref:System.Windows.Media.TranslateTransform> aggiunge un'animazione da 0 a 350 e quindi a 500.  
  
 A causa dell'ordine in cui WPF genera eventi e perché i valori delle proprietà vengono memorizzati nella cache e non vengono ricalcolati, a meno che la proprietà non sia invalidata. L' <xref:System.Windows.Media.Animation.Timeline.Completed> evento viene elaborato per primo perché è stato attivato dalla sequenza temporale radice (il primo <xref:System.Windows.Media.Animation.Storyboard> ). A questo punto, la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà restituisce comunque il valore animato perché non è ancora stata invalidata. Il secondo <xref:System.Windows.Media.Animation.Storyboard> Usa il valore memorizzato nella cache come valore iniziale e inizia l'animazione.  
  
<a name="performancesection"></a>

## <a name="performance"></a>Prestazioni  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Continuazione dell'esecuzione delle animazioni dopo lo spostamento da una pagina  

 Quando si esce da un oggetto <xref:System.Windows.Controls.Page> che contiene animazioni in esecuzione, le animazioni continueranno a essere riprodotte fino a quando non viene sottoposto a <xref:System.Windows.Controls.Page> Garbage Collection. A seconda del sistema di navigazione in uso, una pagina da cui ci si è spostati potrebbe rimanere in memoria per un tempo indefinito, usando le risorse con le relative animazioni. Ciò è più evidente quando una pagina contiene animazioni in esecuzione continua.  
  
 Per questo motivo, è consigliabile usare l' <xref:System.Windows.FrameworkElement.Unloaded> evento per rimuovere le animazioni quando ci si sposta da una pagina.  
  
 Per rimuovere un'animazione, sono disponibili modi diversi. È possibile usare le tecniche seguenti per rimuovere le animazioni che appartengono a un <xref:System.Windows.Media.Animation.Storyboard> .  
  
- Per rimuovere un'attività <xref:System.Windows.Media.Animation.Storyboard> avviata con un trigger di evento, vedere [procedura: rimuovere uno storyboard](/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Per usare il codice per rimuovere un oggetto <xref:System.Windows.Media.Animation.Storyboard> , vedere il <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> metodo.  
  
 La tecnica successiva può essere usata indipendentemente dalla modalità di avviamento dell'animazione.  
  
- Per rimuovere le animazioni da una proprietà specifica, usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo. Specificare la proprietà che viene animata come primo parametro e `null` come secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
 Per ulteriori informazioni sulle diverse modalità di animazione delle proprietà, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Uso di Compose HandoffBehavior con risorse di sistema  

 Quando si applica un oggetto <xref:System.Windows.Media.Animation.Storyboard> , <xref:System.Windows.Media.Animation.AnimationTimeline> o <xref:System.Windows.Media.Animation.AnimationClock> a una proprietà utilizzando <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> , tutti <xref:System.Windows.Media.Animation.Clock> gli oggetti associati in precedenza a tale proprietà continuano a utilizzare le risorse di sistema. il sistema di temporizzazione non rimuoverà automaticamente questi clock.  
  
 Per evitare problemi di prestazioni quando si applica un numero elevato di orologi usando <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> , è necessario rimuovere gli orologi di composizione dalla proprietà animata dopo che sono stati completati. Esistono diverse modalità di rimozione di un orologio.  
  
- Per rimuovere tutti gli orologi da una proprietà, usare il <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> metodo o dell'oggetto animato. Specificare la proprietà che viene animata come primo parametro e `null` come secondo. In questo modo tutti gli orologi dell'animazione vengono rimossi dalla proprietà.  
  
- Per rimuovere un oggetto specifico <xref:System.Windows.Media.Animation.AnimationClock> da un elenco di orologi, utilizzare la <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di <xref:System.Windows.Media.Animation.AnimationClock> per recuperare un oggetto <xref:System.Windows.Media.Animation.ClockController> , quindi chiamare il <xref:System.Windows.Media.Animation.ClockController.Remove%2A> metodo dell'oggetto <xref:System.Windows.Media.Animation.ClockController> . Questa operazione viene in genere eseguita nel <xref:System.Windows.Media.Animation.Clock.Completed> gestore eventi per un clock. Si noti che solo gli orologi radice possono essere controllati da un oggetto <xref:System.Windows.Media.Animation.ClockController> ; la <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà di un clock figlio restituirà `null` . Si noti inoltre che l' <xref:System.Windows.Media.Animation.Clock.Completed> evento non verrà chiamato se la durata effettiva del clock è sempre.  In tal caso, l'utente dovrà determinare quando chiamare <xref:System.Windows.Media.Animation.ClockController.Remove%2A> .  
  
 Si tratta principalmente di un problema relativo alle animazioni su oggetti di lunga durata.  Quando un oggetto viene raccolto nel Garbage Collector, anche gli orologi vengono disconnessi e raccolti nel Garbage Collector stesso.  
  
 Per ulteriori informazioni sugli oggetti Clock, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
