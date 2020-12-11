---
title: Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 3d038f0e1687efb0c2516602e8d5cbf24a60b36c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967582"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] offre due meccanismi paralleli per modificare l'aspetto visivo di un controllo che riceve lo stato attivo della tastiera. Il primo meccanismo consiste nell'usare i metodi di impostazione delle proprietà per le proprietà, ad esempio <xref:System.Windows.UIElement.IsKeyboardFocused%2A> all'interno dello stile o del modello applicato al controllo. Il secondo meccanismo consiste nel fornire uno stile separato come valore della <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà; lo stile di visualizzazione dello stato attivo crea una struttura ad albero visuale separata per uno strumento decorativo che disegna sopra il controllo, anziché modificare la struttura ad albero visuale del controllo o di un altro elemento dell'interfaccia utente sostituendo tale struttura. Questo argomento descrive gli scenari appropriati a ogni meccanismo.  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>Scopo dello stile di visualizzazione dello stato attivo  
 La funzionalità dello stile di visualizzazione dello stato attivo offre un "modello a oggetti" comune per introdurre un feedback utente visivo, basato sul passaggio tramite tastiera a un qualsiasi elemento dell'interfaccia utente. Questo è possibile senza bisogno di applicare un nuovo modello al controllo, né di conoscere la composizione specifica del modello.  
  
 Dal momento però che la funzionalità dello stile di visualizzazione dello stato attivo funziona a prescindere dai modelli di controllo, il feedback visivo che è possibile visualizzare per un controllo usando uno stile di visualizzazione dello stato attivo è necessariamente limitato. La funzionalità sovrappone una struttura ad albero visuale diversa (uno strumento decorativo visuale) sulla struttura ad albero visuale creata dal rendering di un controllo tramite il relativo modello. Si definisce questa struttura ad albero visuale separata usando uno stile che riempie la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Proprietà.  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>Comportamento predefinito dello stile di visualizzazione dello stato attivo  
 Gli stili di visualizzazione dello stato attivo funzionano solo quando l'azione di impostazione dello stato attivo è stata iniziata dalla tastiera. Qualsiasi azione del mouse o modifica dello stato attivo a livello di codice disabilita la modalità degli stili di visualizzazione dello stato attivo. Per altre informazioni sulle differenze tra le modalità dello stato attivo, vedere [Cenni preliminari sullo stato attivo](focus-overview.md).  
  
 I temi dei controlli includono un comportamento predefinito dello stile di visualizzazione dello stato attivo che diventa lo stile di visualizzazione dello stato attivo per tutti i controlli del tema. Questo stile del tema è identificato dal valore della chiave statica <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A> . Quando si dichiara uno stile di visualizzazione dello stato attivo personalizzato a livello di applicazione, questo sostituisce il comportamento dello stile predefinito dei temi. In alternativa, se si definisce l'intero tema, è necessario usare questa stessa chiave per definire lo stile del comportamento predefinito per tutto il tema.  
  
 Nei temi, lo stile di visualizzazione dello stato attivo predefinito in genere è molto semplice. Di seguito è riportata un'approssimazione generica:  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>
## <a name="when-to-use-focus-visual-styles"></a>Quando usare gli stili di visualizzazione dello stato attivo  
 Dal punto di vista concettuale, l'aspetto degli stili di visualizzazione dello stato attivo applicati ai controlli deve essere coerente da un controllo all'altro. Un modo per garantire la coerenza consiste nel modificare lo stile di visualizzazione dello stato attivo solo se si sta componendo un tema completo, in cui ogni controllo definito nel tema ottiene lo stesso stile di visualizzazione dello stato attivo o una variazione di uno stile visivamente coerente tra i vari controlli. In alternativa, si può usare lo stesso stile (o stili simili) per assegnare uno stile a ogni elemento della pagina o di un'interfaccia utente in grado di ricevere lo stato attivo tramite tastiera.  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>L'impostazione di su singoli stili di controllo che non fanno parte di un tema non è l'utilizzo previsto degli stili di visualizzazione dello stato attivo. Un comportamento visivo incoerente tra controlli può infatti creare confusione nell'esperienza utente relativamente allo stato attivo. Se si intendono comportamenti specifici del controllo per lo stato attivo della tastiera che sono deliberatamente non coerenti in un tema, un approccio molto migliore consiste nell'usare i trigger negli stili per le singole proprietà dello stato di input, ad esempio <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocused%2A> .  
  
 Gli stili di visualizzazione dello stato attivo funzionano esclusivamente per lo stato attivo da tastiera. Come tali, costituiscono un tipo di funzionalità di accessibilità. Se si vogliono apportare modifiche all'interfaccia utente per qualsiasi tipo di stato attivo, tramite mouse, tastiera o a livello di codice, è preferibile usare non gli stili di visualizzazione dello stato attivo, bensì setter e trigger all'interno degli stili oppure modelli che funzionino in base al valore delle proprietà generali dello stato attivo, ad esempio <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>Come creare uno stile di visualizzazione dello stato attivo  
 Lo stile creato per uno stile di visualizzazione dello stato attivo deve sempre essere <xref:System.Windows.Style.TargetType%2A> di <xref:System.Windows.Controls.Control> . Lo stile deve essere costituito principalmente da un oggetto <xref:System.Windows.Controls.ControlTemplate> . Il tipo di destinazione non viene specificato come tipo in cui lo stile di visualizzazione dello stato attivo viene assegnato a <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> .  
  
 Poiché il tipo di destinazione è sempre <xref:System.Windows.Controls.Control> , è necessario applicare uno stile usando proprietà comuni a tutti i controlli (usando le proprietà della <xref:System.Windows.Controls.Control> classe e le relative classi di base). È necessario creare un modello che funzioni correttamente come sovrapposizione a un elemento dell'interfaccia utente e che non nasconda le aree funzionali del controllo. In generale, questo vuol dire che il feedback visivo deve essere visualizzato all'esterno dei margini del controllo o sotto forma di effetti temporanei o non intrusivi, che non blocchino l'hit testing sul controllo a cui viene applicato lo stile di visualizzazione dello stato attivo. Le proprietà che è possibile usare nell'associazione di modelli che sono utili per determinare il dimensionamento e il posizionamento del modello di sovrapposizione sono <xref:System.Windows.FrameworkElement.ActualHeight%2A> ,, <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.Controls.Control.Padding%2A> .  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternative all'uso di uno stile di visualizzazione dello stato attivo  
 Per le situazioni in cui non è appropriato usare uno stile di visualizzazione dello stato attivo, perché si sta assegnando uno stile solo a singoli controlli o perché si vuole un controllo maggiore sul modello del controllo, sono disponibili molte altre proprietà e tecniche accessibili che creano un comportamento visivo in risposta alle modifiche apportate allo stato attivo.  
  
 Trigger, setter e setter di eventi sono illustrati in dettaglio in [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview). La gestione degli eventi indirizzati è illustrata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Se si è interessati specificamente allo stato attivo della tastiera, la <xref:System.Windows.UIElement.IsKeyboardFocused%2A> proprietà di dipendenza può essere utilizzata per una proprietà <xref:System.Windows.Trigger> . Un trigger di proprietà in uno stile o in un modello rappresenta una tecnica più appropriata per la definizione di un comportamento dello stato attivo della tastiera specifico per un singolo controllo, che potrebbe non corrispondere visivamente al comportamento dello stato attivo della tastiera di altri controlli.  
  
 Un'altra proprietà di dipendenza simile è <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> , che può essere appropriata da usare se si vuole richiamare visivamente lo stato attivo della tastiera in un punto qualsiasi all'interno della composizione o all'interno dell'area funzionale del controllo. Ad esempio, è possibile inserire un <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> trigger in modo che un pannello che raggruppa diversi controlli venga visualizzato in modo diverso, anche se lo stato attivo della tastiera potrebbe essere più preciso su un singolo elemento all'interno di tale pannello.  
  
 È anche possibile usare gli eventi <xref:System.Windows.UIElement.GotKeyboardFocus> e <xref:System.Windows.UIElement.LostKeyboardFocus> (nonché gli equivalenti di anteprima). È possibile utilizzare questi eventi come base per un oggetto <xref:System.Windows.EventSetter> oppure è possibile scrivere gestori per gli eventi nel code-behind.  
  
### <a name="other-focus-properties"></a>Altre proprietà dello stato attivo  
 Per tutte le possibili cause di modifica dello stato attivo per produrre un comportamento visivo, è necessario basare un setter o un trigger sulla <xref:System.Windows.UIElement.IsFocused%2A> proprietà di dipendenza oppure, in alternativa, sugli <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> eventi o utilizzati per un oggetto <xref:System.Windows.EventSetter> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Cenni preliminari sullo stato attivo](focus-overview.md)
- [Cenni preliminari sull'input](input-overview.md)
