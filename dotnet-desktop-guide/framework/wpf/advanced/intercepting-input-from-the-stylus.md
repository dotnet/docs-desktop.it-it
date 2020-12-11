---
title: Intercettazione dell'input dello stilo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: f05a3c25a61e90ec91cd1db725ba9a40763f0a7f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951822"
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo

L' <xref:System.Windows.Input.StylusPlugIns> architettura fornisce un meccanismo per l'implementazione del controllo di basso livello sull' <xref:System.Windows.Input.Stylus> input e la creazione di oggetti di input penna digitali <xref:System.Windows.Ink.Stroke> . La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classe fornisce un meccanismo per implementare il comportamento personalizzato e applicarlo al flusso di dati provenienti dal dispositivo stilo per ottenere prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Architettura](#Architecture)  
  
- [Implementazione di plug-in dello stilo](#ImplementingStylusPlugins)  
  
- [Aggiunta del plug-in a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>

## <a name="architecture"></a>Architettura  

 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>È l'evoluzione delle API [StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) , descritte in [accesso e manipolazione dell'input penna](/previous-versions/ms818317(v%3dmsdn.10)).  
  
 Ogni <xref:System.Windows.UIElement> ha una <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà che è un oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> . È possibile aggiungere un oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> alla proprietà di un elemento <xref:System.Windows.UIElement.StylusPlugIns%2A> per modificare <xref:System.Windows.Input.StylusPoint> i dati durante la generazione. <xref:System.Windows.Input.StylusPoint> i dati sono costituiti da tutte le proprietà supportate dal digitalizzatore di sistema, inclusi i <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.Y%2A> dati del punto e, nonché i <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> dati.  
  
 Gli <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti vengono inseriti direttamente nel flusso di dati provenienti dal <xref:System.Windows.Input.Stylus> dispositivo quando si aggiunge alla <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> Proprietà. L'ordine in cui i plug-in vengono aggiunti alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta determina l'ordine in cui riceveranno i <xref:System.Windows.Input.StylusPoint> dati. Se ad esempio si aggiunge un plug-in di filtro che limita l'input a una determinata area, quindi si aggiunge un plug-in che riconosce i movimenti quando vengono scritti, il plug-in che riconosce i movimenti riceverà dati filtrati <xref:System.Windows.Input.StylusPoint> .  
  
<a name="ImplementingStylusPlugins"></a>

## <a name="implementing-stylus-plug-ins"></a>Implementazione di plug-in dello stilo  

 Per implementare un plug-in, derivare una classe da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> . Questa classe viene applicata o il flusso di dati in entrata da <xref:System.Windows.Input.Stylus> . In questa classe è possibile modificare i valori dei <xref:System.Windows.Input.StylusPoint> dati.  
  
> [!CAUTION]
> Se un oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> genera o genera un'eccezione, l'applicazione verrà chiusa. È necessario verificare accuratamente i controlli che utilizzano un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e utilizzare un controllo solo se si è certi che <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> non genererà un'eccezione.  
  
 Nell'esempio seguente viene illustrato un plug-in che limita l'input dello stilo modificando <xref:System.Windows.Input.StylusPoint.X%2A> i <xref:System.Windows.Input.StylusPoint.Y%2A> valori e nei <xref:System.Windows.Input.StylusPoint> dati in arrivo dal <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>

## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiunta del plug-in a un InkCanvas  

 Il modo più semplice per usare il plug-in personalizzato consiste nell'implementare una classe che deriva da InkCanvas e aggiungerla alla <xref:System.Windows.UIElement.StylusPlugIns%2A> Proprietà.  
  
 Nell'esempio seguente viene illustrato un oggetto personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si aggiunge un oggetto `FilterInkCanvas` all'applicazione e lo si esegue, si noterà che l'input penna non è limitato a un'area fino a quando l'utente non completa un tratto. Questo è dovuto al fatto <xref:System.Windows.Controls.InkCanvas> che ha una <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà, che è un oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ed è già un membro della <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. L'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aggiunto alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta riceve i <xref:System.Windows.Input.StylusPoint> dati dopo la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ricezione dei dati. Di conseguenza, i <xref:System.Windows.Input.StylusPoint> dati non verranno filtrati fino a quando l'utente non solleva la penna per terminare un tratto. Per filtrare l'input penna quando l'utente lo disegna, è necessario inserire `FilterPlugin` prima di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> .  
  
 Il codice C# seguente illustra un oggetto personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna mentre viene disegnato.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>

## <a name="conclusion"></a>Conclusione  

 Derivando le proprie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserendole in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> raccolte, è possibile migliorare significativamente il comportamento dell'input penna digitale. Si ha accesso ai <xref:System.Windows.Input.StylusPoint> dati generati, offrendo la possibilità di personalizzare l' <xref:System.Windows.Input.Stylus> input. Poiché si dispone di un accesso di basso livello ai <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare la raccolta di input penna e il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e modifica dell'input penna](/previous-versions/ms818317(v%3dmsdn.10))
