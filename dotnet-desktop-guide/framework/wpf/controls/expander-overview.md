---
title: Cenni preliminari sul controllo Expander
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 3fcbcc67b65383133eef8d3e59cb1f8f0ff06f20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964600"
---
# <a name="expander-overview"></a>Cenni preliminari sul controllo Expander
Un <xref:System.Windows.Controls.Expander> controllo fornisce un modo per fornire il contenuto in un'area espandibile simile a una finestra e include un'intestazione.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>Creazione di un controllo Expander semplice  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo semplice. In questo esempio viene creato un oggetto <xref:System.Windows.Controls.Expander> simile a quello illustrato nella figura precedente.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A>E <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di un oggetto <xref:System.Windows.Controls.Expander> possono anche contenere contenuto complesso, ad esempio <xref:System.Windows.Controls.RadioButton> <xref:System.Windows.Controls.Image> oggetti e.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Impostazione della direzione dell'area del contenuto espandibile  
 È possibile impostare l'area di contenuto di un <xref:System.Windows.Controls.Expander> controllo per espanderla in una delle quattro direzioni ( <xref:System.Windows.Controls.ExpandDirection.Down> ,, <xref:System.Windows.Controls.ExpandDirection.Up> <xref:System.Windows.Controls.ExpandDirection.Left> o <xref:System.Windows.Controls.ExpandDirection.Right> ) utilizzando la <xref:System.Windows.Controls.ExpandDirection> Proprietà. Quando l'area di contenuto è compressa, vengono visualizzati solo gli elementi <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il relativo interruttore. Un <xref:System.Windows.Controls.Button> controllo che visualizza una freccia direzionale viene usato come interruttore per espandere o comprimere l'area di contenuto. Quando viene espanso, <xref:System.Windows.Controls.Expander> tenta di visualizzare tutto il contenuto in un'area simile a una finestra.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controllo delle dimensioni di un controllo Expander in un pannello  
 Se un <xref:System.Windows.Controls.Expander> controllo si trova all'interno di un controllo di layout che eredita da <xref:System.Windows.Controls.Panel> , ad esempio <xref:System.Windows.Controls.StackPanel> , non specificare un oggetto <xref:System.Windows.FrameworkElement.Height%2A> in <xref:System.Windows.Controls.Expander> quando la <xref:System.Windows.Controls.Expander.ExpandDirection%2A> proprietà è impostata su <xref:System.Windows.Controls.ExpandDirection.Down> o <xref:System.Windows.Controls.ExpandDirection.Up> . Analogamente, non specificare un oggetto <xref:System.Windows.FrameworkElement.Width%2A> in <xref:System.Windows.Controls.Expander> quando la <xref:System.Windows.Controls.Expander.ExpandDirection%2A> proprietà è impostata su <xref:System.Windows.Controls.ExpandDirection.Left> o <xref:System.Windows.Controls.ExpandDirection.Right> .  
  
 Quando si imposta una dimensione dimensione su un <xref:System.Windows.Controls.Expander> controllo nella direzione in cui viene visualizzato il contenuto espanso, il <xref:System.Windows.Controls.Expander> assume il controllo dell'area utilizzata dal contenuto e visualizza un bordo intorno a esso. Il bordo viene visualizzato anche quando il contenuto è compresso. Per impostare le dimensioni dell'area di contenuto espansa, impostare le dimensioni delle dimensioni sul contenuto di <xref:System.Windows.Controls.Expander> oppure, se si vuole scorrere la funzionalità, sull'oggetto <xref:System.Windows.Controls.ScrollViewer> che racchiude il contenuto.  
  
 Quando un <xref:System.Windows.Controls.Expander> controllo è l'ultimo elemento di un oggetto <xref:System.Windows.Controls.DockPanel> , [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] imposta automaticamente <xref:System.Windows.Controls.Expander> le dimensioni in modo che corrispondano all'area rimanente di <xref:System.Windows.Controls.DockPanel> . Per evitare questo comportamento predefinito, impostare la <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà sull' <xref:System.Windows.Controls.DockPanel> oggetto su `false` o assicurarsi che <xref:System.Windows.Controls.Expander> non sia l'ultimo elemento di un oggetto <xref:System.Windows.Controls.DockPanel> .  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>Creazione di contenuto scorrevole  
 Se il contenuto è troppo grande per le dimensioni dell'area di contenuto, è possibile eseguire il wrapping del contenuto di un oggetto <xref:System.Windows.Controls.Expander> in un oggetto per <xref:System.Windows.Controls.ScrollViewer> fornire contenuto scorrevole. Il <xref:System.Windows.Controls.Expander> controllo non fornisce automaticamente funzionalità di scorrimento. Nella figura seguente viene illustrato un <xref:System.Windows.Controls.Expander> controllo che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
 **Controllo Expander in un controllo ScrollViewer**  
  
 ![Screenshot che mostra un espansore con ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Quando si inserisce un <xref:System.Windows.Controls.Expander> controllo in un oggetto <xref:System.Windows.Controls.ScrollViewer> , impostare la <xref:System.Windows.Controls.ScrollViewer> proprietà della dimensione che corrisponde alla direzione in cui il <xref:System.Windows.Controls.Expander> contenuto viene aperto fino alla dimensione dell' <xref:System.Windows.Controls.Expander> area di contenuto. Se, ad esempio, si imposta la <xref:System.Windows.Controls.Expander.ExpandDirection%2A> proprietà su <xref:System.Windows.Controls.Expander> a <xref:System.Windows.Controls.ExpandDirection.Down> (l'area del contenuto si apre), impostare la <xref:System.Windows.FrameworkElement.Height%2A> proprietà del <xref:System.Windows.Controls.ScrollViewer> controllo sull'altezza necessaria per l'area di contenuto. Se invece si imposta la dimensione Height sul contenuto stesso, non <xref:System.Windows.Controls.ScrollViewer> riconosce questa impostazione e pertanto non fornisce contenuto scorrevole.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo con contenuto complesso e contenente un <xref:System.Windows.Controls.ScrollViewer> controllo. Questo esempio crea un oggetto <xref:System.Windows.Controls.Expander> che è simile all'illustrazione all'inizio di questa sezione.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>Uso delle proprietà di allineamento  
 È possibile allineare il contenuto impostando <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> le <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> proprietà e nel <xref:System.Windows.Controls.Expander> controllo. Quando si impostano queste proprietà, l'allineamento viene applicato all'intestazione e al contenuto espanso.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Procedure](expander-how-to-topics.md)
