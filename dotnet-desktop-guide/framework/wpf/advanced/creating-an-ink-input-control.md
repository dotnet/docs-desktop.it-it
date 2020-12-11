---
title: Creazione di un controllo di input penna
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: d9b18054154e6871925f423f539d44f12adca1f5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964135"
---
# <a name="creating-an-ink-input-control"></a>Creazione di un controllo di input penna

È possibile creare un controllo personalizzato che esegue il rendering dell'input penna in modo dinamico e statico. Ovvero il rendering dell'input penna quando un utente disegna un tratto, causando la visualizzazione dell'input penna in "Flow" dalla penna del tablet e la visualizzazione dell'input penna dopo l'aggiunta al controllo, tramite la penna del tablet, incollato dagli Appunti o caricato da un file. Per eseguire dinamicamente il rendering dell'input penna, il controllo deve usare un oggetto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> . Per eseguire il rendering statico dell'input penna, è necessario eseguire l'override dei metodi di evento dello stilo ( <xref:System.Windows.UIElement.OnStylusDown%2A> , <xref:System.Windows.UIElement.OnStylusMove%2A> e <xref:System.Windows.UIElement.OnStylusUp%2A> ) per raccogliere <xref:System.Windows.Input.StylusPoint> dati, creare tratti e aggiungerli a un oggetto <xref:System.Windows.Controls.InkPresenter> (che esegue il rendering dell'input penna sul controllo).  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Procedura: raccogliere dati dei punti dello stilo e creare tratti di input penna](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Procedura: abilitare il controllo per accettare l'input dal mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Riepilogo](#PuttingItTogether)  
  
- [Uso di plug-in aggiuntivi e DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Conclusione](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>

## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Procedura: raccogliere dati dei punti dello stilo e creare tratti di input penna  

 Per creare un controllo che raccoglie e gestisce i tratti di input penna, effettuare le operazioni seguenti:  
  
1. Derivare una classe da <xref:System.Windows.Controls.Control> o da una delle classi derivate da <xref:System.Windows.Controls.Control> , ad esempio <xref:System.Windows.Controls.Label> .  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Aggiungere un oggetto <xref:System.Windows.Controls.InkPresenter> alla classe e impostare la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà sul nuovo <xref:System.Windows.Controls.InkPresenter> .  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Allineare l'oggetto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> di a chiamando il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkPresenter> <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> metodo e aggiungere l'oggetto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. Questo consente <xref:System.Windows.Controls.InkPresenter> a di visualizzare l'input penna quando i dati del punto dello stilo vengono raccolti dal controllo.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusDown%2A>.  In questo metodo acquisire lo stilo con una chiamata a <xref:System.Windows.Input.Stylus.Capture%2A> . Acquisendo lo stilo, il controllo continuerà a ricevere <xref:System.Windows.UIElement.StylusMove> <xref:System.Windows.UIElement.StylusUp> eventi e anche se lo stilo lascia i limiti del controllo. Questa operazione non è strettamente obbligatoria, ma è quasi sempre necessaria per un'esperienza utente ottimale. Creare un nuovo oggetto <xref:System.Windows.Input.StylusPointCollection> per raccogliere <xref:System.Windows.Input.StylusPoint> i dati. Infine, aggiungere il set di <xref:System.Windows.Input.StylusPoint> dati iniziale a <xref:System.Windows.Input.StylusPointCollection> .  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Eseguire l'override del <xref:System.Windows.UIElement.OnStylusMove%2A> metodo e aggiungere i <xref:System.Windows.Input.StylusPoint> dati all' <xref:System.Windows.Input.StylusPointCollection> oggetto creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Eseguire l'override del <xref:System.Windows.UIElement.OnStylusUp%2A> metodo e creare un nuovo oggetto <xref:System.Windows.Ink.Stroke> con i <xref:System.Windows.Input.StylusPointCollection> dati. Aggiungere il nuovo <xref:System.Windows.Ink.Stroke> creato alla <xref:System.Windows.Controls.InkPresenter.Strokes%2A> raccolta di <xref:System.Windows.Controls.InkPresenter> e acquisire lo stilo della versione.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>

## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Procedura: abilitare il controllo per accettare l'input dal mouse  

 Se si aggiunge il controllo precedente all'applicazione, lo si esegue e si usa il mouse come dispositivo di input, si noterà che i tratti non sono salvati in modo permanente. Per salvare in modo permanente i tratti quando il mouse viene usato come dispositivo di input, eseguire le operazioni seguenti:  
  
1. Eseguire l'override di <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> e creare un nuovo oggetto <xref:System.Windows.Input.StylusPointCollection> per ottenere la posizione del mouse quando si è verificato l'evento e creare un oggetto <xref:System.Windows.Input.StylusPoint> utilizzando i dati del punto e aggiungere <xref:System.Windows.Input.StylusPoint> a <xref:System.Windows.Input.StylusPointCollection> .  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseMove%2A>. Ottiene la posizione del mouse quando si è verificato l'evento e crea un oggetto <xref:System.Windows.Input.StylusPoint> utilizzando i dati del punto.  Aggiungere all' <xref:System.Windows.Input.StylusPoint> <xref:System.Windows.Input.StylusPointCollection> oggetto creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  Creare un nuovo oggetto <xref:System.Windows.Ink.Stroke> con i <xref:System.Windows.Input.StylusPointCollection> dati e aggiungere il nuovo <xref:System.Windows.Ink.Stroke> creato alla <xref:System.Windows.Controls.InkPresenter.Strokes%2A> raccolta di <xref:System.Windows.Controls.InkPresenter> .  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>

## <a name="putting-it-together"></a>Riepilogo  

 L'esempio seguente è un controllo personalizzato che raccoglie l'input penna quando l'utente usa il mouse o la penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>

## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Uso di plug-in aggiuntivi e DynamicRenderers  

 Analogamente a InkCanvas, il controllo personalizzato può avere <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti personalizzati e aggiuntivi <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> . Aggiungerli alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. L'ordine degli <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ha effetto sull'aspetto dell'input penna quando ne viene eseguito il rendering. Si supponga di avere un oggetto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> denominato `dynamicRenderer` e un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> chiamato `translatePlugin` che compensa l'input penna dalla penna del tablet. Se `translatePlugin` è il primo <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nell'oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> e `dynamicRenderer` è il secondo, l'input penna "Flows" verrà sfalsato quando l'utente sposta la penna. Se `dynamicRenderer` è il primo e `translatePlugin` è il secondo, l'input penna non verrà sfalsato fino a quando l'utente non solleva la penna.  
  
<a name="AdvancedInkHandling_Conclusion"></a>

## <a name="conclusion"></a>Conclusione  

 È possibile creare un controllo che raccoglie ed esegue il rendering dell'input penna eseguendo l'override dei metodi di evento dello stilo. Creando un controllo personalizzato, derivando le proprie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserendoli in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> , è possibile implementare praticamente qualsiasi comportamento immaginabile con l'input penna digitale. Si ha accesso ai <xref:System.Windows.Input.StylusPoint> dati generati, offrendo la possibilità di personalizzare l' <xref:System.Windows.Input.Stylus> input e di eseguirne il rendering sullo schermo in modo appropriato per l'applicazione. Poiché si dispone di un accesso di basso livello ai <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare la raccolta di input penna ed eseguirne il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e modifica dell'input penna](/previous-versions/ms818317(v=msdn.10))
